---
title: 'Lync Server 2013: Requisitos técnicos para el estacionamiento de llamadas'
TOCTitle: Requisitos técnicos para el estacionamiento de llamadas
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48274965
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos técnicos para el estacionamiento de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Esta sección describe los siguientes requisitos técnicos para Estacionamiento de llamadas:

  - Requisitos de hardware

  - Requisitos de software

  - Requisitos de los puertos

  - Requisitos de archivos de audio

## Requisitos de hardware

Los requisitos de hardware de la Aplicación de estacionamiento de llamadas son los mismos que los de Servidores front-end. Encontrará más información sobre los requisitos de hardware, consulte [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad.

## Requisitos de software

Los requisitos de sistema operativo y requisitos previos de software de la Aplicación de estacionamiento de llamadas son los mismos que los de Servidores front-end. Encontrará más información sobre los requisitos de software, consulte [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.

Todos los Servidores front-end y los servidores Standard Edition en los que está implementado Aplicación de estacionamiento de llamadas deben tener el Tiempo de ejecución de Windows Media Format instalado para servidores que ejecutan Windows Server 2008 R2 o Microsoft Media Foundation para servidores que ejecutan Windows Server 2012 o Windows Server 2012 R2. Para Windows Server 2008 R2, el Tiempo de ejecución de Windows Media Format está instalado como parte de la experiencia de escritorio de Windows. Se requiere el Tiempo de ejecución de Windows Media Format o Microsoft Media Foundation para archivos de audio de Windows Media (.wma) que Estacionamiento de llamadas reproduce para música en espera.

## Requisitos de los puertos

La Aplicación de estacionamiento de llamadas utiliza el siguiente puerto:

  - **Puerto 5075**   Usado para solicitudes de escucha SIP.


> [!NOTE]
> Este puerto es una configuración predeterminada que puede cambiar mediante el cmdlet <STRONG>Set-CsApplicationServer</STRONG>. Para obtener detalles acerca de este cmdlet, vea la documentación de Shell de administración de Lync Server.



## Requisitos de archivos de audio

La Aplicación de estacionamiento de llamadas solo admite archivos de audio de Windows Media (.wma) para música en espera. Puede usar Microsoft Expression Encoder 4 para personalizar los archivos para la música en espera. Para descargar Expression Encoder 4, vea "Expression Encoder 4" en [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843). Use la herramienta para convertir el archivo en un formato .wma. El formato recomendado para los archivos de música en espera de Estacionamiento de llamadas es Media Audio 9, 44 kHz, 16 bits, mono, CBR, 32 kbps.


> [!NOTE]
> El archivo convertido se reproduce por el teléfono solo a 16 kHz, aunque se grabó a 44 kHz.


