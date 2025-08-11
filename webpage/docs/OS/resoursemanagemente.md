---
title: Gerenciamento de recursos
slug: /resourcemanagement
sidebar_position: 1
---

# Introdução aos sistemas operacionais


:::info Operating Systems Crash Course

<div style={{ textAlign: 'center' }}>
    <iframe 
        style={{
            display: 'block',
            margin: 'auto',
            width: '100%',
            height: '50vh',
        }}
        src="https://www.youtube.com/embed/26QPDBe-NB8" 
        frameborder="0" 
        allowFullScreen>
    </iframe>
</div>
<br/>

:::

Um sistema operacional (SO) é, fundamentalmente, um **software** que atua como
uma **ponte ou intermediário entre as aplicações do usuário e o hardware do
computador**. Ele é responsável por **controlar e sincronizar o hardware** e
assegurar que os programas funcionem corretamente. Ao contrário da percepção
comum, o sistema operacional não se resume apenas à sua interface visual, como
a interface gráfica do usuário (GUI) ou o terminal (Shell), que são programas
que rodam sobre ele e utilizam suas funcionalidades. As funções do SO incluem:

1.  **Abstração e Extensão da Máquina**:
    *   Um dos principais papéis do SO é **esconder a complexidade do
        hardware** e apresentar aos programadores e usuários um conjunto de
        **recursos abstratos, limpos, elegantes e consistentes**.
    *   Nos primeiros computadores sem SO, cada programa precisava de drivers
        específicos e configurava o hardware completo para rodar. A
        complexidade crescente do hardware e das aplicações tornou o SO
        necessário para **facilitar o desenvolvimento e o uso diário**.
    *   Por exemplo, para criar, ler ou escrever arquivos, o usuário não
        precisa lidar com os detalhes técnicos de discos rígidos (HDDs) ou
        SSDs; o SO fornece a abstração de "arquivos". Essa abstração torna
        tarefas quase impossíveis em duas gerenciáveis: definir e implementar
        as abstrações, e usá-las para resolver o problema.

2.  **Gerenciamento de Recursos (Multiplexação)**:
    *   O SO é crucial para **gerenciar e alocar de forma ordenada e controlada
        os recursos do sistema**, como processadores, memória principal e
        dispositivos de entrada/saída (E/S).
    *   Ele **impede o caos** que ocorreria se múltiplos programas tentassem
        acessar os mesmos recursos simultaneamente (por exemplo, várias
        impressões na mesma impressora).
    *   O gerenciamento de recursos envolve a **multiplexação**, que pode ser
        de duas formas:
        *   **Multiplexação no tempo**: Diferentes programas ou usuários se
            revezam no uso de um recurso. Por exemplo, a CPU é alocada a um
            programa por um tempo, depois a outro, e assim por diante. Filas de
            impressão são outro exemplo.
        *   **Multiplexação no espaço**: O recurso é dividido, e cada programa
            recebe uma parte dele. Exemplos incluem a divisão da memória
            principal entre vários programas e a alocação de espaço em disco
            para arquivos de diferentes usuários.

3.  **Provisão de Serviços e Facilidades**:
    *   Os SOs oferecem serviços essenciais para a execução de programas, como
        **gerenciamento de processos, controle de E/S, manipulação de arquivos,
        comunicação entre processos (IPC) e segurança**.
    *   **Processos**: Um conceito fundamental, um processo é um programa em
        execução. Cada processo tem seu próprio espaço de endereçamento
        (memória que pode ler e escrever) e um conjunto de recursos (registros,
        arquivos abertos, etc.). O SO gerencia a criação, suspensão, reinício e
        término de processos.
    *   **Espaços de Endereçamento**: O SO gerencia o espaço de endereçamento
        que cada processo pode usar. A técnica de **memória virtual** permite
        que programas maiores que a memória física sejam executados, movendo
        partes do código e dados entre a memória principal e o armazenamento
        não volátil (SSD/disco) conforme necessário.
    *   **Sistema de Arquivos**: Organiza e gerencia arquivos em hierarquias de
        diretórios (pastas), permitindo operações como criar, remover, ler e
        escrever arquivos, e ocultando as peculiaridades dos dispositivos de
        armazenamento. Dispositivos de E/S podem ser modelados como "arquivos
        especiais" para padronizar o acesso.
    *   **Proteção e Segurança**: Garante que informações e recursos sejam
        acessíveis apenas a usuários autorizados, protegendo o sistema contra
        intrusos e erros.

**Modos de Operação**:

Os sistemas operacionais operam em dois modos principais de CPU:
*   **Modo Núcleo (Kernel Mode/Modo Supervisor)**: Neste modo, a CPU tem acesso
    completo a todas as instruções e funcionalidades do hardware. O próprio
    sistema operacional geralmente executa neste modo.
*   **Modo Usuário (User Mode)**: Programas de usuário rodam neste modo, que
    possui um conjunto restrito de instruções e funcionalidades. Instruções que
    envolvem E/S ou proteção de memória são geralmente proibidas, e não é
    permitido ao programa de usuário mudar para o modo núcleo diretamente.
*   **Chamadas de Sistema (System Calls)**: Para que um programa de usuário
    obtenha serviços do sistema operacional, ele deve fazer uma "chamada de
    sistema". Essa chamada faz com que a CPU mude do modo usuário para o modo
    núcleo, permitindo que o SO execute a tarefa privilegiada e, em seguida,
    retorne o controle ao programa de usuário.

Em essência, o sistema operacional é a camada de software vital que **gerencia
os recursos do computador, fornece abstrações simplificadas para o hardware e
garante um ambiente seguro e eficiente** para a execução de outros softwares e
a interação do usuário. O **kernel** é considerado o verdadeiro descendente dos
primeiros sistemas operacionais e representa a parte do SO que opera no modo
núcleo.

## 1. Um breve histórico

A história e a evolução dos sistemas operacionais (SOs) são intrinsecamente
ligadas ao desenvolvimento e à complexidade crescentes do hardware dos
computadores. Inicialmente, os computadores não possuíam sistemas operacionais;
hoje, eles são softwares essenciais que agem como intermediários entre as
aplicações do usuário e o hardware, gerenciando recursos e provendo abstrações.

**1. Primeira Geração (1945-1955): Tubos a Vácuo**
Os primeiros computadores, como os mainframes, **não tinham qualquer tipo de
sistema operacional**. Cada usuário tinha acesso exclusivo à máquina por um
período definido e precisava ir ao computador com seu programa e dados,
frequentemente em cartões perfurados, fitas de papel ou magnéticas. O programa
era carregado manualmente, e a máquina configurada para a tarefa. A depuração
era feita por meio de painéis de controle. A programação era realizada em
linguagem de máquina ou até mesmo por meio da **conexão de circuitos elétricos
em painéis**. Linguagens simbólicas, montadores e compiladores foram
desenvolvidos, e bibliotecas de suporte para operações de entrada e saída (E/S)
começaram a surgir, embora as máquinas ainda executassem **um trabalho por
vez**.

**2. Segunda Geração (1955-1965): Transistores e Sistemas em Lotes**
A introdução do **transistor** em meados da década de 1950 revolucionou os
computadores, tornando-os mais confiáveis e comercialmente viáveis. Surgiu uma
clara separação de funções entre designers, operadores e programadores.
Operadores profissionais passaram a ser responsáveis por rodar os "mainframes".
Para otimizar o tempo de máquina, que era muito caro, a solução adotada foi o **sistema em lote (batch system)**. Trabalhos eram coletados e lidos em fita magnética por um computador menos dispendioso (ex: IBM 1401) e então transferidos para máquinas mais potentes (ex: IBM 7094) para o processamento principal. Após a execução, a saída era escrita em outra fita e impressa offline. Um programa especial, **o ancestral do sistema operacional moderno**, lia os trabalhos da fita, controlava sua execução e gravava o uso dos recursos. **Cartões de controle** (ex: $JOB, $FORTRAN, $LOAD, $RUN, $END) eram usados para instruir esse "monitor" ou "programa de monitoramento", que foram os precursores dos interpretadores de linha de comando modernos (shells). Exemplos de SOs dessa era foram FMS (Fortran Monitor System) e IBSYS para o IBM 7094.

**3. Terceira Geração (1965-1980): Circuitos Integrados (ICs) e Multiprogramação**
Nessa década, a IBM introduziu o **System/360**, uma série de máquinas
compatíveis em software que variavam em preço e desempenho, visando unificar
linhas de produtos científicas e comerciais. A intenção era ter um **único SO,
o OS/360**, para toda a linha, mas a complexidade do projeto resultou em um
conjunto de sistemas operacionais. O OS/360 e sistemas similares popularizaram
técnicas como a **multiprogramação**.
*   **Multiprogramação**: Para evitar ociosidade da CPU durante operações de
    E/S, a memória foi particionada para conter múltiplos trabalhos
    simultaneamente. Enquanto um trabalho esperava por E/S, outro poderia usar
    a CPU, mantendo-a quase 100% ocupada. Isso exigiu hardware especial para
    proteção de memória.
*   **Spooling (Simultaneous Peripheral Operation On Line)**: Capacidade de ler
    trabalhos de cartões para o disco assim que chegavam, e carregar novos
    trabalhos do disco para a memória quando um anterior terminava. Também
    usado para a saída, eliminando a necessidade de máquinas como o IBM 1401
    para E/S offline.
*   **Timesharing**: Uma variante da multiprogramação que permitia a
    **múltiplos usuários interagir com o computador simultaneamente** através
    de terminais online. O CPU alternava entre os usuários, proporcionando um
    serviço rápido e interativo. O primeiro sistema de timesharing de propósito
    geral foi o **CTSS** (Compatible Time Sharing System) do M.I.T..
*   **MULTICS (MULTiplexed Information and Computing Service)**: Um ambicioso
    projeto de "computador utilitário" do M.I.T., Bell Labs e General Electric.
    Embora não tenha sido um sucesso comercial inicial, o **MULTICS introduziu
    muitas ideias seminais**, como os níveis de privilégio de segurança e
    sistemas de arquivos hierárquicos. Sua influência foi enorme em sistemas
    operacionais subsequentes, **especialmente o UNIX e seus derivados (Linux,
    macOS, iOS, FreeBSD)**.
*   **Minicomputadores**: Crescimento fenomenal com máquinas como o DEC PDP-1 e
    PDP-11.
*   **UNIX**: Desenvolvido na AT&T Bell Laboratories no final da década de 1960
    por Ken Thompson, originalmente para o PDP-7 e PDP-11. Sua popularidade
    cresceu devido à sua disponibilidade e facilidade de modificação. Sendo
    escrito em linguagem C, o **UNIX se tornou altamente portável** para
    diversas arquiteturas de máquina, tornando-se o **primeiro sistema
    operacional a ter o mesmo conceito em múltiplas plataformas de hardware**.
    Inspirou muitos e foi uma das raízes do movimento de software livre e de
    código aberto. Versões importantes incluem o System V (AT&T) e BSD
    (Berkeley Software Distribution). O padrão **POSIX** foi desenvolvido para
    garantir compatibilidade entre versões do UNIX. MINIX, um clone do UNIX
    para fins educacionais criado por Tanenbaum, inspirou o desenvolvimento do
    **Linux**.

**4. Quarta Geração (1980-Presente): Computadores Pessoais**
O desenvolvimento de circuitos de **LSI (Large Scale Integration)**
possibilitou o surgimento dos **computadores pessoais (PCs)**, tornando a
computação acessível a indivíduos e pequenos negócios.
*   **CP/M**: O Digital Research's CP/M-80 foi o primeiro SO importante para
    microcomputadores com CPUs como 8080/Z-80, dominando o mercado por cerca de
    5 anos.
*   **MS-DOS/PC DOS**: A Microsoft desenvolveu o MS-DOS (ou PC DOS para IBM)
    para o IBM PC, projetado para ser similar ao CP/M-80. A estratégia da
    Microsoft de licenciar o MS-DOS para empresas de computadores o ajudou a
    dominar o mercado do IBM PC.
*   **Interface Gráfica do Usuário (GUI)**: Inventada por Doug Engelbart e
    desenvolvida na Xerox PARC. Steve Jobs viu seu potencial e a Apple a
    popularizou com o **Macintosh**, que foi um enorme sucesso por ser
    "amigável ao usuário".
*   **Microsoft Windows**: Inicialmente, Windows era um ambiente gráfico que
    rodava sobre o MS-DOS. A partir do Windows 95, tornou-se uma versão
    independente com muitas funcionalidades de sistema operacional. Versões
    posteriores como Windows NT (com base em ideias do VAX VMS), Windows XP,
    Vista, 7, 8, 10 e 11 continuaram a evolução.
*   **Família UNIX em PCs**: Linux e macOS (baseado em Unix-like
    Darwin/FreeBSD) se tornaram os outros principais sistemas operacionais para
    PCs, sendo fortes em servidores de rede e ambientes corporativos, além de
    desktops e notebooks. Muitos usuários UNIX, especialmente programadores,
    preferem interfaces de linha de comando, mas também há o **X Window System
    (X11)** e ambientes de desktop completos como Gnome ou KDE.
*   **Sistemas Operacionais de Rede e Distribuídos**: Surgiram para gerenciar
    coleções de computadores. Sistemas de rede permitem aos usuários estarem
    cientes de múltiplas máquinas e logar remotamente. Sistemas distribuídos,
    em contraste, aparecem como um único sistema uniprocessador para os
    usuários, escondendo a complexidade da rede.

**5. Quinta Geração (1990-Presente): Computadores Móveis e Ascensão da Virtualização**
*   **Sistemas Operacionais Portáteis**: O início dos anos 90 viu o surgimento
    de PDAs com sistemas como o EPOC (que evoluiu para Symbian). Palm OS e
    Windows CE (posteriormente Windows Mobile) também foram proeminentes.
*   **Smartphones**: Em 2007, a Apple lançou o iPhone com seu **iOS** (baseado
    em Unix-like Darwin) e uma interface gráfica inovadora. Um ano depois, o
    **Android** (baseado em um kernel Linux modificado) foi lançado pelo
    Google. Ambos dominam atualmente o mercado de smartphones, superando o
    Symbian OS e Blackberry OS.
*   **Internet das Coisas (IoT) e Sistemas Embarcados**: Bilhões de objetos
    físicos conectados à rede (geladeiras, termostatos, câmeras de segurança) e
    dispositivos não conectados (fornos de micro-ondas, máquinas de lavar)
    contêm pequenos computadores e geralmente rodam sistemas operacionais
    pequenos. Muitos desses sistemas não aceitam software instalado pelo
    usuário e são projetados para hardware fixo, o que simplifica o design ao
    não exigir proteção entre aplicações. Exemplos incluem Embedded Linux, QNX
    e VxWorks, além de SOs de pegada muito pequena como RIOT e TinyOS.
*   **Sistemas Operacionais de Tempo Real (Real-Time Operating Systems -
    RTOS)**: Caracterizam-se por ter o tempo como um parâmetro chave, com
    prazos que devem ser cumpridos (sistemas de tempo real rígido, ex: controle
    industrial, aviônicos) ou que, se ocasionalmente perdidos, não causam danos
    permanentes (sistemas de tempo real suave, ex: áudio digital, smartphones).
*   **Sistemas Operacionais para Cartões Inteligentes (Smart Cards)**: Os
    menores SOs, com severas restrições de processamento e memória. Alguns são
    orientados a Java, executando applets.

*   **A Ascensão da Virtualização**: Originalmente, os sistemas operacionais
    rodavam diretamente no hardware. Com a virtualização, o sistema operacional
    passou a ser executado **dentro de si mesmo sob o controle de um
    hipervisor**, ao invés de ser controlado diretamente pelo hardware.
    *   A IBM introduziu o conceito de **máquina virtual** em 1968 com o CP/CMS
        e posteriormente com o VM/370 em mainframes.
    *   Em PCs x86, a VMware popularizou essa tecnologia em 1999. Outros
        produtos incluem Xen, KVM e Hyper-V.
    *   A virtualização tornou-se uma **característica chave nos sistemas
        operacionais modernos** (ex: KVM e LXC no Linux, Hyper-V no Windows
        Server).
    *   A diferença entre máquinas virtuais, monitores e sistemas operacionais
        começou a desaparecer, com softwares de máquina virtual desempenhando o
        papel de gerenciar recursos de hardware e agendamento.

**O Conceito de Kernel**
É importante notar que a **interface gráfica do usuário (GUI)** ou o terminal
(Shell) **não são o sistema operacional em si**, mas programas que rodam sobre
ele e utilizam suas funcionalidades. O **verdadeiro descendente dos primeiros
sistemas operacionais é conhecido hoje como "Kernel"**. O kernel representa a
parte do SO que opera no **modo núcleo (kernel mode/modo supervisor)**, tendo
acesso completo a todas as instruções e funcionalidades do hardware. Programas
de usuário, por sua vez, rodam no **modo usuário (user mode)**, que possui um
conjunto restrito de instruções e funcionalidades. Para obter serviços do
sistema operacional, um programa de usuário deve fazer uma **chamada de sistema
(system call)**, que faz a CPU mudar do modo usuário para o modo núcleo.

## 2. Breve resumo de hardware

O **kernel** do sistema operacional atua como o **intermediador** fundamental entre o software de aplicação e o **hardware** da máquina. Ele é responsável por **gerenciar todos os recursos do sistema complexo** e fornecer uma **interface abstrata e limpa** para os programadores e programas, escondendo os detalhes intrincados do funcionamento do hardware.

Para cumprir suas funções, o kernel precisa interagir de forma íntima e controlada com diversos tipos de hardware:

*   **Processadores (CPUs)**:
    *   **O que são**: Considerados o "cérebro" do computador, os processadores buscam e executam instruções da memória. Cada CPU possui um conjunto específico de instruções que pode executar. Processadores modernos podem ter múltiplos núcleos (multicore) ou serem multithreaded.
    *   **Interação do Kernel**: A maioria das CPUs possui (pelo menos) dois modos de operação: **modo núcleo (kernel mode/supervisor mode)** e **modo usuário (user mode)**. O sistema operacional, especificamente o kernel, opera no modo núcleo, onde tem **acesso completo a todas as instruções do conjunto e a todas as funcionalidades do hardware**. Programas de usuário, por sua vez, sempre rodam no modo usuário, com um **subconjunto restrito de instruções e funcionalidades** (instruções de E/S e proteção de memória são geralmente proibidas). Para que um programa de usuário solicite um serviço que exija privilégios do modo núcleo, ele deve fazer uma **chamada de sistema (system call)**, que causa uma "trap" para o kernel, mudando a CPU para o modo núcleo. O kernel também é responsável por **salvar e restaurar todos os registradores da CPU** quando alterna entre programas (context switch), garantindo o **escalonamento e a multiprogramação**.

*   **Memória Principal (RAM)**:
    *   **O que é**: É o principal local de trabalho do sistema de memória, onde os programas em execução são armazenados temporariamente. É uma memória volátil, o que significa que perde seu conteúdo ao desligar.
    *   **Interação do Kernel**: O kernel é o responsável por **gerenciar e proteger a memória**, dividindo-a entre vários programas em execução (multiplexação no espaço) para evitar interferências e permitir que todos residam ao mesmo tempo.

*   **Memória Cache**:
    *   **O que é**: Uma memória de alta velocidade, localizada dentro ou muito próxima à CPU, que armazena as linhas de memória mais usadas para acesso rápido.
    *   **Interação do Kernel**: Embora seja controlada principalmente pelo hardware, o sistema operacional utiliza o conceito de cache extensivamente, mantendo, por exemplo, **partes de arquivos frequentemente usados na memória principal** para evitar acessos repetidos ao armazenamento secundário.

*   **Memórias Não Voláteis (ROM, EEPROM, Flash, CMOS)**:
    *   **O que são**: Tipos de memória que **não perdem seu conteúdo quando a energia é desligada**. A **ROM (Read Only Memory)** é programada de fábrica e contém o **bootstrap loader (BIOS)**, um programa usado para iniciar o computador. A **EEPROM (Electrically Erasable PROM)** e a **Flash memory** são reescrevíveis e usadas em dispositivos portáteis, SSDs e também para o BIOS. A **CMOS** é volátil, mas alimentada por bateria para manter informações como hora/data e parâmetros de configuração de boot.
    *   **Interação do Kernel**: O kernel interage com a firmware do sistema (BIOS ou UEFI) durante o processo de **boot** para carregar-se na memória. O kernel precisa **detectar e inicializar** vários recursos e dispositivos através da BIOS.

*   **Memória Virtual**:
    *   **O que é**: Uma técnica que permite que programas maiores que a memória física sejam executados, usando o armazenamento não volátil (SSD ou disco) como uma extensão da RAM. A **MMU (Memory Management Unit)**, parte da CPU, realiza o remapeamento de endereços em tempo real.
    *   **Interação do Kernel**: O kernel é o responsável por **gerenciar o espaço de endereçamento de processos** e a memória virtual, movendo partes do programa entre a memória principal e o armazenamento secundário conforme necessário.

*   **Armazenamento Não Volátil (Discos Magnéticos/HDDs, SSDs, Memória Persistente)**:
    *   **O que são**: Dispositivos para armazenamento de dados de longo prazo. Os **discos magnéticos (HDDs)** são dispositivos mecânicos com platters giratórios. Os **SSDs (Solid State Drives)** armazenam dados em memória Flash eletrônica, sendo muito mais rápidos que os HDDs. A **memória persistente** (como Intel Optane) é uma camada mais recente e rápida que mantém o conteúdo sem energia.
    *   **Interação do Kernel**: O kernel esconde as particularidades desses dispositivos e apresenta uma **abstração de arquivos** aos programadores. Ele aloca espaço em disco, rastreia qual programa está usando quais blocos de disco. O sistema de arquivos, que agrupa arquivos em diretórios (pastas), é um conceito chave gerenciado pelo sistema operacional.

*   **Dispositivos de Entrada/Saída (E/S)**:
    *   **O que são**: Todos os dispositivos físicos que permitem ao computador receber entrada e produzir saída, como teclados, monitores, impressoras, mouses, etc.. Geralmente consistem em um **controlador** (um chip que controla fisicamente o dispositivo e aceita comandos do SO) e o **próprio dispositivo**.
    *   **Interação do Kernel**: O kernel possui um **subsistema de E/S** para gerenciar esses dispositivos. A comunicação entre o kernel e os controladores é feita por meio de **drivers de dispositivo**, que são softwares específicos para cada tipo de controlador e geralmente rodam em modo núcleo. Existem diferentes métodos de E/S, como **busy waiting (polling)**, **interrupções** (onde o dispositivo sinaliza o CPU quando termina a operação), e **DMA (Direct Memory Access)** (onde um chip dedicado gerencia o fluxo de dados entre memória e controlador sem intervenção constante da CPU).

*   **Barramentos (Buses)**:
    *   **O que são**: Caminhos de comunicação que conectam a CPU, a memória e os dispositivos de E/S. Exemplos incluem **PCIe, USB, SATA e DMI**.
    *   **Interação do Kernel**: O kernel deve estar **ciente de todos os barramentos** para configuração e gerenciamento. Ele usa esses barramentos para se comunicar com os controladores de dispositivos e transferir dados.

Em suma, o kernel atua como o **gerente mestre** do hardware, orquestrando e controlando o acesso a cada componente para garantir que os programas de usuário possam funcionar de forma eficiente e segura, sem a necessidade de lidar diretamente com a complexidade do hardware subjacente.

## 3. User space vs kernel

:::info Operating Systems Crash Course

<div style={{ textAlign: 'center' }}>
    <iframe 
        style={{
            display: 'block',
            margin: 'auto',
            width: '100%',
            height: '50vh',
        }}
        src="https://www.youtube.com/embed/H4SDPLiUnv4" 
        frameborder="0" 
        allowFullScreen>
    </iframe>
</div>
<br/>

:::

A separação dos níveis de segurança em um sistema operacional (SO) é um conceito fundamental para garantir a estabilidade, a integridade e a segurança do sistema como um todo. Essa divisão é implementada por meio de diferentes modos de operação da Unidade Central de Processamento (CPU), principalmente o **modo núcleo** (ou modo supervisor) e o **modo usuário**.

### A Necessidade da Separação de Níveis de Segurança

Desde os primeiros computadores, que **não possuíam sistemas operacionais** e onde cada programa precisava do hardware completo para funcionar, a complexidade crescente do hardware e das aplicações exigiu o desenvolvimento de SOs. Inicialmente, em mainframes como o IBM 7090/7094, a **ausência de hardware de proteção** significava que um único programa com falhas poderia corromper o sistema operacional e causar uma pane na máquina.

Com o tempo, percebeu-se a necessidade de **gerenciar e proteger a memória, dispositivos de E/S e outros recursos**, especialmente quando múltiplos usuários ou programas compartilham o mesmo sistema. Sem essa gestão, a execução simultânea de múltiplos programas, por exemplo, tentando imprimir na mesma impressora, resultaria em "caos completo". A solução para isso foi a incorporação de **recursos de segurança** nos sistemas operacionais para controlar o acesso a arquivos e prevenir o uso indevido de recursos, garantindo a integridade dos sistemas.

### Modos de Operação da CPU

A distinção entre os modos de operação da CPU é crucial para a segurança e o funcionamento do SO:

*   **Modo Núcleo (Kernel Mode / Modo Supervisor)**:
    *   Neste modo, a **CPU tem acesso completo a todas as instruções do seu conjunto e a todas as funcionalidades do hardware**.
    *   É o modo onde o sistema operacional, especificamente o **kernel** – o verdadeiro descendente dos primeiros sistemas operacionais – opera.
    *   No modo núcleo, é possível enviar **qualquer instrução** que a máquina seja capaz de executar.
    *   A ativação de recursos de hardware para proteção de memória foi um avanço crucial, como visto com a introdução do IBM 360, que permitiu a **multiprogramação** ao manter múltiplos programas na memória de forma segura.

*   **Modo Usuário (User Mode)**:
    *   Os **programas de usuário sempre rodam no modo usuário**, que permite a execução de apenas um **subconjunto das instruções** e o acesso a um **subconjunto restrito das funcionalidades**.
    *   Instruções que envolvem operações de E/S e proteção de memória são geralmente **proibidas** no modo usuário.
    *   Também é **proibido** alterar o bit do Program Status Word (PSW) para entrar no modo núcleo diretamente do modo usuário.
    *   Essa restrição impede que um programa de usuário malicioso ou com falhas acesse ou danifique áreas críticas da memória ou do hardware pertencentes ao sistema operacional ou a outros programas.

### Chamadas de Sistema (System Calls)

Para que um programa em modo usuário possa acessar recursos protegidos ou solicitar serviços do sistema operacional que exigem privilégios de modo núcleo, ele deve fazer uma **chamada de sistema (system call)**.

*   **Função**: As chamadas de sistema são a **interface primária entre os programas de aplicação e o kernel** do sistema operacional.
*   **Mecanismo**: Uma chamada de sistema funciona como uma instrução especial (como `syscall` em processadores x86-64) que **causa uma "trap" para o kernel**, fazendo com que a CPU **mude do modo usuário para o modo núcleo**.
*   **Execução e Retorno**: O sistema operacional, agora em modo núcleo, executa o serviço solicitado pelo programa de usuário. Após a conclusão da tarefa, o controle é **retornado ao programa de usuário**, continuando a execução na instrução seguinte à chamada de sistema, e a CPU retorna para o modo usuário.
*   **Abstração**: O sistema operacional atua como um **intermediador**, abstraindo a complexidade do hardware e fornecendo uma **interface limpa e consistente** para os programadores. Isso permite que os desenvolvedores escrevam programas sem se preocuparem com os detalhes intrincados de como o hardware funciona, focando nos problemas de alto nível que seus aplicativos se propõem a resolver.
*   **Exemplos**: Chamadas de sistema são usadas para diversas operações, como criar arquivos (ex: a chamada `mkdir` no terminal), ler e gravar arquivos, gerenciar processos, controlar dispositivos de entrada/saída, e lidar com comunicação entre processos (IPC).

Sistemas como o **MULTICS** foram pioneiros ao introduzir o conceito de **níveis de privilégio de segurança ("ringed-security")**, influenciando grandemente sistemas operacionais subsequentes como o UNIX e seus derivados (Linux, macOS, iOS e FreeBSD). Essa arquitetura de proteção é a base para a segurança e a capacidade dos sistemas operacionais modernos de gerenciar e proteger recursos de forma eficiente e controlada.


