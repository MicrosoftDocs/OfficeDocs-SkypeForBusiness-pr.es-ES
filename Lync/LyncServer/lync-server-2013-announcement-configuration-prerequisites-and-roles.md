---
title: 'Lync Server 2013: Requisitos previos y roles para configurar anuncios'
TOCTitle: Requisitos previos y roles para configurar anuncios
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48275854
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos previos y roles para configurar anuncios en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-25_

El anuncio es una característica de administración de llamadas de Telefonía IP empresarial. Este tema describe lo que necesita preparar antes de poder configurar el anuncio, y las asignaciones de roles que necesita para realizar tareas de configuración.

En esta sección, se da por supuesto que ha leído la documentación de planeación relacionada con el anuncio (consulte [Planificar las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

## Requisitos previos de configuración del anuncio

La Aplicación de anuncio requiere los siguientes componentes:

  - Servicio de aplicaciones

  - Aplicación de grupo de respuesta

  - Almacenamiento de archivos, para los archivos de audio

Todos estos componentes se instalan de forma predeterminada cuando se implementa Telefonía IP empresarial.

## Roles de configuración de anuncios

Puede usar las siguientes herramientas administrativas para configurar anuncios:

  - Panel de control de Lync Server

  - Shell de administración de Lync Server

La configuración de la Aplicación de anuncio requiere una de los siguientes roles administrativos:

  - **CsVoiceAdministrator**   Este rol de administrador puede crear, configurar y administrar todas las configuraciones y directivas relacionadas con la voz, incluida la configuración de anuncio.

  - **CsServerAdministrator**   Este rol de administrador puede administrar, supervisar y solucionar problemas de servidores y servicios, además de configurar todas las opciones de anuncio.

  - **CsAdministrator**   Este rol de administrador puede realizar todas las tareas administrativas y modificar toda la configuración.

  - **CsViewOnlyAdministrator**   Este rol de administrador puede ver la implementación para supervisar su estado.


> [!NOTE]
> Para ver más detalles acerca de los derechos de los usuarios administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planeación del control de acceso basado en roles en Lync Server 2013</A> en la documentación de planeación.



## Vea también

#### Conceptos

[Implementar la telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  

#### Otros recursos

[Planificar las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)

