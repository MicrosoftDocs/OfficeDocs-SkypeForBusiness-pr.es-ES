---
title: 'Lync Server 2013: Implementación del complemento VDI de Lync'
TOCTitle: Implementación del complemento VDI de Lync
ms:assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204683(v=OCS.15)
ms:contentKeyID: 48274477
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementación del complemento VDI de Lync en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-03_

El cliente Lync 2013 admite audio y vídeo en un entorno de Infraestructura de escritorio virtual (VDI). Un usuario puede conectar un dispositivo de audio o vídeo (por ejemplo, auriculares o una cámara) al equipo de acceso (por ejemplo, un equipo con una nueva función o una interfaz de cliente delgada). El usuario puede conectarse a la máquina virtual, iniciar sesión en el cliente de Lync 2013 que se está ejecutando en la máquina virtual y participar en las comunicaciones de vídeo y audio en tiempo real como si el cliente se ejecutara localmente.

El complemento VDI de Lync es una aplicación independiente que se instala en el equipo local y permite el uso de dispositivos de audio y vídeo locales con el cliente de Lync 2013 de la máquina virtual. No es necesario instalar Lync en la máquina local. Una vez que el usuario inicia sesión en el cliente de Lync 2013 que se está ejecutando en la máquina virtual, Lync solicita al usuario que vuelva a introducir sus credenciales para establecer una conexión con el complemento VDI de Lync que se ejecuta en el equipo local. Una vez se establece esta conexión, el usuario estará listo para realizar y recibir llamadas de audio y de vídeo.

## En esta sección

  - [Requisitos previos del componente de VDI de Lync en Lync Server 2013](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [Preparar su entorno Lync Server 2013 para VDI](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [Iniciar sesión y utilizar Lync 2013 en la máquina virtual](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [Solución de problemas del complemento Lync VDI](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [Tecnologías de virtualización admitidas y limitaciones comunes en Lync Server 2013](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

