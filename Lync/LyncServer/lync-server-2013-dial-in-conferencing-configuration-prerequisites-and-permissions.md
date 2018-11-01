---
title: "Lync Server 2013: Requisitos y permisos config. en conferencias de acceso telefónico"
TOCTitle: Requisitos previos y permisos de configuración para conferencias de acceso telefónico
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48276410
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos previos y permisos de configuración para conferencias de acceso telefónico en Lync Server 2013

 

_**Última modificación del tema:** 2012-06-20_

Las conferencias de acceso telefónico local son un componente opcional de la carga de trabajo de conferencias de Lync Server 2013. Los componentes que debe instalar antes de que pueda configurar las conferencias de acceso telefónico local están implementados cuando usa la fea-cs-plan-tool-1st y Generador de topologías para diseñar la topología y configurar el grupo de servidores front-end o el servidor Standard Edition. En este tema se describe lo que tiene que haber realizado antes de poder configurar las conferencias de acceso telefónico local.

En esta sección se presupone que ya ha leído todas las secciones de planeación relacionadas con la carga de trabajo de conferencias y con las conferencias de acceso telefónico local en particular.

## Requisitos previos de configuración para conferencia de acceso telefónico local

La conferencia de acceso telefónico local requiere los siguientes componentes de Lync Server 2013:

  - Servicio de aplicaciones de comunicaciones unificadas (UCAS) (denominado el *servicio de aplicación* )

  - Aplicación Operador de conferencia

  - Aplicación de anuncio de conferencia

  - Página web de configuración de la conferencia de acceso telefónico local

  - Al menos un servidor de mediación de Lync Server 2013 y al menos una puerta de enlace RTC

Implementa estos componentes cuando usa la fea-cs-plan-tool-2nd y Generador de topologías para definir y publicar la topología e implementar un grupo de servidores front-end o un servidor Standard Edition. Si implementa Telefonía IP empresarial, debe implementarlo antes de configurar la conferencia de acceso telefónico local. Si no implementa Telefonía IP empresarial, puede implementar un servidor de mediación y una puerta de enlace de red telefónica conmutada (RTC) cuando implementa el grupo de servidores front-end o el servidor Standard Edition.


> [!NOTE]
> Si actualiza desde Office Communications Server 2007 R2 a Lync Server 2013, implemente la conferencia con acceso telefónico en cada grupo que utilizará para alojar las conferencias de Lync Server 2013. Para obtener información detallada sobre la migración de conferencias con acceso telefónico, vea <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migrar de Office Communications Server 2007 R2 a Lync Server 2013</A>.



En esta sección se presupone que ya he realizado el siguiente procedimiento:

  - Aplicar las últimas actualizaciones al entorno Office Communications Server 2007 R2, si migra a Lync Server 2013.

  - Usar Generador de topologías para diseñar y configurar su topología. Mientras especifica la carga de trabajo de conferencias, debe seleccionar la opción de conferencia de acceso telefónico local. Para más información sobre cómo definir la topología, consulte [Definición y configuración de la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) en la documentación referente a la implementación.

  - Publicar la topología y configurar el grupo de servidores front-end o el servidor Standard Edition. Para más información sobre cómo publicar la topología e instalar Lync Server 2013, consulte [Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación referente a la implementación.
    

    > [!NOTE]
    > Cuando instale la topología publicada, la página web de configuración de la conferencia de acceso telefónico local estará instalada en el grupo de servidores front-end o el servidor Standard Edition como parte de los servicios web.

    
    > [!IMPORTANT]  
    > Si cambia la ruta del almacén de archivos en Generador de topologías después de implementar Lync Server 2013, debe reiniciar las aplicaciones de operador de conferencia y anuncio de conferencia para usar la nueva ruta.
    


  - Implementar Telefonía IP empresarial. Si no implementa Telefonía IP empresarial, ha instalado un servidor de mediación en el servidor front-end Enterprise Edition o el servidor Standard Edition, o ha implementado un servicio de mediación independiente y ha implementado una puerta de enlace RTC. Para obtener información detallada sobre la implementación de Telefonía IP empresarial, consulte [Implementar la telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) en la documentación referente en la implementación. Para más información sobre la instalación de un servidor de mediación independiente y una puerta de enlace RTC, consulte [Implementar servidores de mediación y definir servidores del mismo nivel en Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) en la documentación referente a la implementación.

En el siguiente diagrama se muestran los pasos que debe realizar antes de poder configurar la conferencia de acceso telefónico local y los pasos que debe realizar para configurar la conferencia de acceso telefónico local.

**Implementación de la característica de conferencia de acceso telefónico local**

![Diagrama de flujo de implementación de conferencia de acceso telefónico local](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Diagrama de flujo de implementación de conferencia de acceso telefónico local")

## Permisos para la conferencia de acceso telefónico local

Para configurar la conferencia de acceso telefónico local, debe usar las siguientes herramientas administrativas:

  - Panel de control de Lync Server 2013

  - Shell de administración de Lync Server

Debe usar estas herramientas administrativas para configurar la conferencia de acceso telefónico local, y los planes de marcado, directivas y otras configuraciones que requiera la conferencia de acceso telefónico local.

La configuración de la conferencia de acceso telefónico local requiere cualquiera de los siguientes roles administrativos, según la tarea:

  - **CsVoiceAdministrator**   Este rol de administrador puede crear, configurar y administrar configuraciones y directivas relacionadas con la voz.

  - **CsUserAdministrator**   Este rol de administrador puede habilitar y deshabilitar a los usuarios para Lync Server y asignar directivas existentes, como directivas de conferencia y directivas de PIN a los usuarios.

  - **CsAdministrator**   Este rol de administrador puede realizar todas las tareas de CsVoiceAdministrator y CsUserAdministrator.

## Vea también

#### Conceptos

[Implementar la telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)

