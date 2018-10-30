---
title: 'Lync Server 2013: Requisitos previos de software para la telefonía IP '
TOCTitle: Requisitos previos de software para la telefonía IP empresarial
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48275083
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos previos de software para la telefonía IP empresarial en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-03_

Compruebe que la infraestructura en la que tiene pensado implementar la Telefonía IP empresarial satisface el siguiente software necesario como requisito previo:

  - Lync Server 2013 Standard Edition o Enterprise Edition está instalado y operativo en la red.

  - Tener implementados e instalados en la red perimetral todos los servidores perimetrales, incluidos los Servidores perimetrales que ejecuten el Servidor perimetral de acceso, el Servicio perimetral A/V, el Servicio perimetral de conferencia web, así como un servidor inverso.

  - Se requiere Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 o Microsoft Exchange Server 2013 para integrar la mensajería unificada de Exchange con Lync Server y para proporcionar notificaciones de texto enriquecido e información del registro de llamadas a los extremos del Lync.

  - Haber creado y habilitado uno o varios usuarios en Lync Server.

  - Haber implementado correctamente clientes y dispositivos de Lync.

  - Haber instalado Generador de topologías en un servidor de la red.

## Pasos siguientes: Comprobar los requisitos previos de configuración y seguridad

Tras comprobar los requisitos previos de software de la Telefonía IP empresarial, puede usar la documentación para seguir con la preparación de la implementación de Telefonía IP empresarial:

1.  Comprobar los requisitos previos de seguridad, configuración de usuario y hardware, tal como se describe en [Requisitos previos de seguridad y configuración para telefonía IP empresarial en Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).

2.  Instalar el servidor de mediación, tal como se describe en [Instalar los archivos del servidor de mediación en Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), pero *solo* si desea implementar un servidor de mediación independiente o un grupo de servidores porque los servidores de mediación se han instalado como parte del grupo de servidores front-end o del proceso de implementación del Servidor Standard Edition cuando se colocaron.

3.  Configurar conexiones de enlace troncal para proporcionar conectividad con RTC para los usuarios, tal como se describe en [Configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md).

