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

Quando usamos *Windows*, *Linux* ou *MacOS*; estamos utilizando o que já nos 
acostumamos a chamar de **sistema operacional**, mas você já se perguntou
o que isso significa? Se você tivesse que fazer um sistema operacional do zero,
você saberia o que precisaria implementar? Essa seção visa tornar claro 
exatamente *o que* e *para que* serve um sistema operacional.

Antes de mais nada, vamos entender de onde surgiram os sistemas operacionais.

## 1. Uma breve história...

É completamente impossível dissociar a história dos sistemas operacionais da
história dos próprios computadores digitais. Como vocês já devem ter visto
[em um outro artigo](https://firelink-library.github.io/arch/history), a 
história da computação é bastante antiga, mas os primeiros computadores 
*usáveis* surgiram entre as décadas de 1940 e 1950. Tratavam-se de computadores
que utilizavam **tubos de vácuo** como hoje utilizamos transistores. 

Nessa **primeira geração**, o simples fato de ser possível realizar contas de
forma automatizada já era um enorme avanço. Sendo assim, eles **não tinham 
qualquer tipo de sistema operacional**. Cada usuário tinha acesso exclusivo à
máquina por um período definido e precisava ir ao computador com seu programa e
dados, frequentemente em cartões perfurados, fitas de papel ou magnéticas. O
programa era carregado manualmente, e a máquina configurada para a tarefa. A
depuração era feita por meio de painéis de controle. A programação era
realizada em linguagem de máquina ou até mesmo por meio da **conexão de
circuitos elétricos em painéis**.

A **segunda geração** de computadores introduziu os computadores *eletrônicos*,
mas para o estudo dos sistemas operacionais é mais importante notar o 
surgimento de **sistemas em lote (batch)**. Operadores profissionais passaram a
ser responsáveis por rodar os "mainframes". Para otimizar o tempo de máquina,
que era muito caro, trabalhos eram coletados e lidos em fita magnética por um
computador menos dispendioso (ex: IBM 1401) e então transferidos para máquinas
mais potentes (ex: IBM 7094) para o processamento principal. Após a execução, a
saída era escrita em outra fita e impressa offline. Um programa especial, **o
ancestral do sistema operacional moderno**, lia os trabalhos da fita,
controlava sua execução e gravava o uso dos recursos. **Cartões de controle**
(ex: $JOB, $FORTRAN, $LOAD, $RUN, $END) eram usados para instruir esse
"monitor" ou "programa de monitoramento", que foram os precursores dos
interpretadores de linha de comando modernos (shells). Exemplos de SOs dessa
era foram FMS (Fortran Monitor System) e IBSYS para o IBM 7094.

A **terceira geração** dos computadores surgiu com o advento dos processadores
em *circuitos integrados* e os **sistemas multiprogramáveis**. Nessa geração, a
IBM introduziu o **System/360**, uma série de máquinas compatíveis em software
que variavam em preço e desempenho, visando unificar linhas de produtos
científicas e comerciais. A intenção era ter um **único SO, o OS/360**, para
toda a linha, mas a complexidade do projeto resultou em um conjunto de sistemas
operacionais. O OS/360 e sistemas similares popularizaram técnicas como a
**multiprogramação**. Para evitar ociosidade da CPU durante operações de E/S
(I/O), a memória foi particionada para conter múltiplos trabalhos
simultaneamente. Enquanto um trabalho esperava por E/S, outro poderia usar a
CPU, mantendo-a quase 100% ocupada. Isso exigiu hardware especial para **proteção
de memória**.

Foi nessa geração que surgiram sistemas operacionais que influenciam 
profundamente os sistemas modernos. Destacam-se:

*   **MULTICS (MULTiplexed Information and Computing Service)**: Um ambicioso
    projeto de "computador utilitário" do M.I.T., Bell Labs e General Electric.
    Embora não tenha sido um sucesso comercial inicial, o **MULTICS introduziu
    muitas ideias seminais**, como os níveis de privilégio de segurança e
    sistemas de arquivos hierárquicos. Sua influência foi enorme em sistemas
    operacionais subsequentes, **especialmente o UNIX e seus derivados (Linux,
    macOS, iOS, FreeBSD)**.
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

Nessa geração também surgiram conceitos de extrema importância para definir
os sistemas operacionais modernos. A saber:
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
*   **Minicomputadores**: Crescimento fenomenal com máquinas como o DEC PDP-1 e
    PDP-11.

A **quarta geração** da computação trouxe o domínio dos *computadores pessoais*
(PCs). Com a disseminação da computação a esse nível, a preocupação passou a ser
em criar sistemas **com maior compatibilidade** e **com facilidade de uso**.

A princípio, os PCs eram itens de nicho, utilizados apenas por entusiastas. A 
interface dos sistemas operacionais da época refletiam bem essa natureza. O
CP/M-80 foi o primeiro SO importante para microcomputadores com CPUs como
8080/Z-80, dominando o início do mercado de PCs. A Microsoft desenvolveu o
MS-DOS (ou PC DOS para IBM) para o IBM PC, projetado para ser similar ao
CP/M-80. A estratégia da Microsoft de licenciar o MS-DOS para empresas de
computadores o ajudou a dominar o mercado do IBM PC.

O uso de interfaces gráficas foi capitaneado por Doug Engelbart e desenvolvida
na Xerox PARC. Steve Jobs viu seu potencial e a Apple a popularizou com o
**Macintosh**, que foi um enorme sucesso por ser "amigável ao usuário". Seguindo
a tendência estabelecida pela Apple, a Microsoft desenvolveu o um ambiente
gráfico que rodava sobre o MS-DOS, o **Windows**. A partir do Windows 95,
tornou-se uma versão independente com muitas funcionalidades de sistema
operacional. Versões posteriores como Windows NT (com base em ideias do VAX
VMS), Windows XP, Vista, 7, 8, 10 e 11 continuaram a evolução.


Linux e macOS (baseado em Unix-like Darwin/FreeBSD) se tornaram os outros
principais sistemas operacionais para PCs, sendo fortes em servidores de rede e
ambientes corporativos, além de desktops e notebooks. Muitos usuários UNIX,
especialmente programadores, preferem interfaces de linha de comando, mas
também há o **X Window System (X11)** (e, mais recentemente, o **Wayland**) e
ambientes de desktop completos como Gnome ou KDE.

## 2. Definindo um SO

A história dos sistemas operacionais escancara a natureza deste tipo de
software. Por ela, é possível perceber que trata-se de um sistema que surgiu 
como uma forma de **prover acesso ao hardware** para os usuários e evoluiu com 
o tempo para também ser capaz de **escalonar processos**. Sendo assim, podemos
definir um sistema operacional como:

Um **software** que atua como uma **ponte ou intermediário entre as aplicações
do usuário e o hardware do computador**. Ele é responsável por **controlar e
sincronizar o hardware** e assegurar que os programas funcionem
corretamente. Ao contrário da percepção comum, o sistema operacional não se
resume apenas à sua interface visual, como a interface gráfica do usuário
(GUI) ou o terminal (Shell), que são programas que rodam sobre ele e
utilizam suas funcionalidades. As funções do SO incluem:

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

Neste momento, estamos mais interessados na capacidade do sistema operacional
de **gerenciar recursos** através de **abstrações de sistemas periféricos**.
Para entendermos o nível de complexidade dessa tarefa, vamos brevemente revisar
que tipos de dispositivos podem ser integrados ao computador e devem, portanto,
ser gerenciados pelo sistema operacional.

## 3. Montanha de periféricos

O **kernel** do sistema operacional atua como o **intermediador** fundamental
entre o software de aplicação e o **hardware** da máquina. Ele é responsável
por **gerenciar todos os recursos do sistema** e fornecer uma **interface
abstrata e limpa** para os programadores e programas, escondendo os detalhes
do funcionamento do hardware.

Para cumprir suas funções, o kernel precisa interagir de forma íntima e
controlada com diversos tipos de hardware:

*   **Processadores (CPUs)**:
    *   **O que são**: Considerados o "cérebro" do computador, os processadores
        buscam e executam instruções da memória. Cada CPU possui um conjunto
        específico de instruções que pode executar. Processadores modernos
        podem ter múltiplos núcleos (multicore) ou serem multithreaded.
    *   **Interação do Kernel**: A maioria das CPUs possui (pelo menos) dois
        modos de operação: **modo núcleo (kernel mode/supervisor mode)** e
        **modo usuário (user mode)**. O sistema operacional, especificamente o
        kernel, opera no modo núcleo, onde tem **acesso completo a todas as
        instruções do conjunto e a todas as funcionalidades do hardware**.
        Programas de usuário, por sua vez, sempre rodam no modo usuário, com um
        **subconjunto restrito de instruções e funcionalidades** (instruções de
        E/S e proteção de memória são geralmente proibidas). Para que um
        programa de usuário solicite um serviço que exija privilégios do modo
        núcleo, ele deve fazer uma **chamada de sistema (system call)**, que
        causa uma "trap" para o kernel, mudando a CPU para o modo núcleo. O
        kernel também é responsável por **salvar e restaurar todos os
        registradores da CPU** quando alterna entre programas (context switch),
        garantindo o **escalonamento e a multiprogramação**.

*   **Memória Principal (RAM)**:
    *   **O que é**: É o principal local de trabalho do sistema de memória,
        onde os programas em execução são armazenados temporariamente. É uma
        memória volátil, o que significa que perde seu conteúdo ao desligar.
    *   **Interação do Kernel**: O kernel é o responsável por **gerenciar e
        proteger a memória**, dividindo-a entre vários programas em execução
        (multiplexação no espaço) para evitar interferências e permitir que
        todos residam ao mesmo tempo.

*   **Memória Cache**:
    *   **O que é**: Uma memória de alta velocidade, localizada dentro ou muito
        próxima à CPU, que armazena as linhas de memória mais usadas para
        acesso rápido.
    *   **Interação do Kernel**: Embora seja controlada principalmente pelo
        hardware, o sistema operacional utiliza o conceito de cache
        extensivamente, mantendo, por exemplo, **partes de arquivos
        frequentemente usados na memória principal** para evitar acessos
        repetidos ao armazenamento secundário.

*   **Memórias Não Voláteis (ROM, EEPROM, Flash, CMOS)**:
    *   **O que são**: Tipos de memória que **não perdem seu conteúdo quando a
        energia é desligada**. A **ROM (Read Only Memory)** é programada de
        fábrica e contém o **bootstrap loader (BIOS)**, um programa usado para
        iniciar o computador. A **EEPROM (Electrically Erasable PROM)** e a
        **Flash memory** são reescrevíveis e usadas em dispositivos portáteis,
        SSDs e também para o BIOS. A **CMOS** é volátil, mas alimentada por
        bateria para manter informações como hora/data e parâmetros de
        configuração de boot.
    *   **Interação do Kernel**: O kernel interage com a firmware do sistema
        (BIOS ou UEFI) durante o processo de **boot** para carregar-se na
        memória. O kernel precisa **detectar e inicializar** vários recursos e
        dispositivos através da BIOS.

*   **Memória Virtual**:
    *   **O que é**: Uma técnica que permite que programas maiores que a
        memória física sejam executados, usando o armazenamento não volátil
        (SSD ou disco) como uma extensão da RAM. A **MMU (Memory Management
        Unit)**, parte da CPU, realiza o remapeamento de endereços em tempo
        real.
    *   **Interação do Kernel**: O kernel é o responsável por **gerenciar o
        espaço de endereçamento de processos** e a memória virtual, movendo
        partes do programa entre a memória principal e o armazenamento
        secundário conforme necessário.

*   **Armazenamento Não Volátil (Discos Magnéticos/HDDs, SSDs, Memória Persistente)**:
    *   **O que são**: Dispositivos para armazenamento de dados de longo prazo.
        Os **discos magnéticos (HDDs)** são dispositivos mecânicos com platters
        giratórios. Os **SSDs (Solid State Drives)** armazenam dados em memória
        Flash eletrônica, sendo muito mais rápidos que os HDDs. A **memória
        persistente** (como Intel Optane) é uma camada mais recente e rápida
        que mantém o conteúdo sem energia.
    *   **Interação do Kernel**: O kernel esconde as particularidades desses
        dispositivos e apresenta uma **abstração de arquivos** aos
        programadores. Ele aloca espaço em disco, rastreia qual programa está
        usando quais blocos de disco. O sistema de arquivos, que agrupa
        arquivos em diretórios (pastas), é um conceito chave gerenciado pelo
        sistema operacional.

*   **Dispositivos de Entrada/Saída (E/S)**:
    *   **O que são**: Todos os dispositivos físicos que permitem ao computador
        receber entrada e produzir saída, como teclados, monitores,
        impressoras, mouses, etc.. Geralmente consistem em um **controlador**
        (um chip que controla fisicamente o dispositivo e aceita comandos do
        SO) e o **próprio dispositivo**.
    *   **Interação do Kernel**: O kernel possui um **subsistema de E/S** para
        gerenciar esses dispositivos. A comunicação entre o kernel e os
        controladores é feita por meio de **drivers de dispositivo**, que são
        softwares específicos para cada tipo de controlador e geralmente rodam
        em modo núcleo. Existem diferentes métodos de E/S, como **busy waiting
        (polling)**, **interrupções** (onde o dispositivo sinaliza o CPU quando
        termina a operação), e **DMA (Direct Memory Access)** (onde um chip
        dedicado gerencia o fluxo de dados entre memória e controlador sem
        intervenção constante da CPU).

*   **Barramentos (Buses)**:
    *   **O que são**: Caminhos de comunicação que conectam a CPU, a memória e
        os dispositivos de E/S. Exemplos incluem **PCIe, USB, SATA e DMI**.
    *   **Interação do Kernel**: O kernel deve estar **ciente de todos os
        barramentos** para configuração e gerenciamento. Ele usa esses
        barramentos para se comunicar com os controladores de dispositivos e
        transferir dados.

## 4. Uma palavra sobre segurança

Um programa que serve para gerenciar a integração de **hardware** do computador
e expor abstrações deve, por definição, ter acesso irrestrito a esses 
dispositivos. Esse fato por si mesmo não configura um problema, mas quando 
consideramos que os computadores modernos devem executar milhares de programas
feito por autores distintos, surge o problema de **manter a segurança do
sistema**. Uma das heranças do **MULTICS** é justamente a divisão de privilégios
de segurança. A divisão é feita em dois modos:
*   **Modo Núcleo (Kernel Mode/Modo Supervisor)**: Neste modo, a CPU tem acesso
    completo a todas as instruções e funcionalidades do hardware. O próprio
    sistema operacional geralmente executa neste modo.
*   **Modo Usuário (User Mode)**: Programas de usuário rodam neste modo, que
    possui um conjunto restrito de instruções e funcionalidades. Instruções que
    envolvem E/S ou proteção de memória são geralmente proibidas, e não é
    permitido ao programa de usuário mudar para o modo núcleo diretamente.

Resta aqui a pergunta: se o usuário não tem acesso direto aos dispositivos 
protegidos pelo kernel, como pode um programa, por exemplo, ler um arquivo 
armazenado dentro do *SSD* de um computador? A resposta para esta dúvida está
na existência de uma interface do *kernel* chamada **System Call**. Para que um
programa de usuário obtenha serviços do sistema operacional, ele deve fazer uma
"chamada de sistema". Essa chamada faz com que a CPU mude do modo usuário para
o modo núcleo, permitindo que o SO execute a tarefa privilegiada e, em seguida,
retorne o controle ao programa de usuário.

:::info How a Single Bit Inside Your Processor Shields Your Operating System's Integrity

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

:::info Searchable Linux Syscall Table

[Link](https://filippo.io/linux-syscall-table/)

Esse material não deve ser lido de cabo a rabo, mas serve como uma referência
dos *syscall* de Linux. Talvez a existência desse autoestudo indique que vai
ter alguma atividade relacionada com *syscalls*. Algo para se pensar...

:::
