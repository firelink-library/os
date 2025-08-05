---
title: Do kernel ao userspace
slug: /os-intro
sidebar_position: 1
---

import Admonition from '@theme/Admonition';

<Admonition type="tip" title="Está com pouco tempo?">
  Eu dividi os materiais dessa seção por nível de importância. Se estiver com
  pouco tempo, veja os conteúdos que estão assim:

  <Admonition type="danger" title="">
    {/* Aqui você pode colocar um exemplo ou deixar vazio */}
  </Admonition>

  Os que estão assim:

  <Admonition type="info" title="">
    {/* Aqui você pode colocar um exemplo ou deixar vazio */}
  </Admonition>

  Dão mais contexto ao conteúdo essencial, mas podem ser vistos após o encontro
</Admonition>

# Do kernel ao userspace

## 1. O processo de boot

:::danger How does Linux boot process work?


<div style={{ textAlign: 'center' }}>
    <iframe 
        style={{
            display: 'block',
            margin: 'auto',
            width: '100%',
            height: '50vh',
        }}
        src="https://www.youtube.com/embed/XpFsMB6FoOs" 
        frameborder="0" 
        allowFullScreen>
    </iframe>
</div>
<br/>

:::

:::info How does a PC Boot?

<div style={{ textAlign: 'center' }}>
    <iframe 
        style={{
            display: 'block',
            margin: 'auto',
            width: '100%',
            height: '50vh',
        }}
        src="https://www.youtube.com/embed/rmgla4yeCXw" 
        frameborder="0" 
        allowFullScreen>
    </iframe>
</div>
<br/>

:::

:::info O processo de boot do Arch Linux

Para este autoestudo, sugere-se uma leitura atenta, entrando nos links
sugeridos pelo próprio artigo para entender melhor todas as etapas de boot.

[Link](https://wiki.archlinux.org/title/Arch_boot_process)

:::

## 2. Early userspace (initramfs)

:::info Initial ramdisk

[Link](https://en.wikipedia.org/wiki/Initial_ramdisk)

:::

:::info mkinitcpio

Para este autoestudo, sugere-se uma leitura atenta, entrando nos links
sugeridos pelo próprio artigo para entender melhor todas as etapas de boot.

[Link](https://wiki.archlinux.org/title/Mkinitcpio)

:::

## 3. PID 1

:::danger init

[Link](https://wiki.archlinux.org/title/Init)

:::

:::info Systemd explained

<div style={{ textAlign: 'center' }}>
    <iframe 
        style={{
            display: 'block',
            margin: 'auto',
            width: '100%',
            height: '50vh',
        }}
        src="https://www.youtube.com/embed/Kzpm-rGAXos" 
        frameborder="0" 
        allowFullScreen>
    </iframe>
</div>
<br/>

:::

## 4. Late userspace

:::danger File & File systems

<div style={{ textAlign: 'center' }}>
    <iframe 
        style={{
            display: 'block',
            margin: 'auto',
            width: '100%',
            height: '50vh',
        }}
        src="https://www.youtube.com/embed/KN8YgJnShPM" 
        frameborder="0" 
        allowFullScreen>
    </iframe>
</div>
<br/>

:::

:::info Explaining file systems

<div style={{ textAlign: 'center' }}>
    <iframe 
        style={{
            display: 'block',
            margin: 'auto',
            width: '100%',
            height: '50vh',
        }}
        src="https://www.youtube.com/embed/_h30HBYxtws" 
        frameborder="0" 
        allowFullScreen>
    </iframe>
</div>
<br/>

:::

:::info Protection rings

[Link](https://en.wikipedia.org/wiki/Protection_ring)

:::
