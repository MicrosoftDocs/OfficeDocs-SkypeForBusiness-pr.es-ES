---
title: 'Lync Server 2013: Requisitos técnicos para la aplicación Anuncio'
TOCTitle: Requisitos técnicos para la aplicación Anuncio
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48277251
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos técnicos para la aplicación Anuncio en Lync Server 2013

 

_**Última modificación del tema:** 2013-11-07_

En esta sección se describen los siguientes requisitos técnicos de la Aplicación de anuncio:

  - Requisitos de hardware

  - Requisitos de software

  - Requisitos de los puertos

  - Requisitos de archivos de audio

## Requisitos de hardware

Los requisitos de hardware de la Aplicación de anuncio son los mismos que los de Servidores front-end. Para obtener información detallada sobre los requisitos de hardware, vea [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad.

## Requisitos de software

Los requisitos de sistema operativo y requisitos previos de software de la Aplicación de anuncio son los mismos que los de Servidores front-end. Para obtener información detallada sobre los requisitos de software, consulte [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.

Todos los servidores Servidores front-end o Standard Edition que ejecutan la Aplicación de anuncio necesitan tener instalado el tiempo de ejecución de Windows Media Format para los servidores que ejecutan Windows Server 2008 R2, o Microsoft Media Foundation para los servidores que ejecutan Windows Server 2012 o Windows Server 2012 R2. Para Windows Server 2008 R2, el tiempo de ejecución de Windows Media Format se instala como parte de la experiencia de escritorio de Windows. Se necesita el tiempo de ejecución de Windows Media Format o Microsoft Media Foundation para los archivos Windows Media Audio (.wma) que reproduce la Aplicación de anuncio para anuncios y música.

## Requisitos de los puertos

La Aplicación de anuncio utiliza el siguiente puerto:

  - **Puerto 5071**   Se utiliza para solicitudes de escucha SIP


> [!NOTE]
> Este puerto es el predeterminado, pero puede cambiarlo utilizando el cmdlet <STRONG>Set-CsApplicationServer</STRONG>. Si desea información detallada sobre este cmdlet, vea la documentación de Shell de administración de Lync Server.



## Requisitos de archivos de audio

La Aplicación de anuncio es compatible con los formatos de archivo Wave (.wav) y Windows Media audio (.wma) para la música y los anuncios. Los requisitos de archivos de audio para Aplicación de anuncio son los mismos que los de Aplicación de grupo de respuesta. Si desea información detallada, vea [Requisitos técnicos para grupos de respuesta en Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

