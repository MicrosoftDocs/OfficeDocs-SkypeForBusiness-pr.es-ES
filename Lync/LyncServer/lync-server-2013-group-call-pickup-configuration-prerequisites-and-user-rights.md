---
title: "Derechos de usuario y requisitos de configuración de respuesta de llamadas en grupo"
TOCTitle: "Droits d’ut. requis et élém. prérequis pour conf. de la prise d’appel de gr."
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945641(v=OCS.15)
ms:contentKeyID: 52061704
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Derechos de usuario y requisitos previos de la configuración de respuesta de llamadas en grupo

 

_**Última modificación del tema:** 2013-01-30_

La respuesta de llamadas en grupo en una característica de administración de llamadas que se instala de manera predeterminada al implementar Telefonía IP empresarial. En este tema se describen los elementos necesarios para poder configurar la respuesta de llamadas en grupo, así como los derechos de usuario necesarios para llevar a cabo las tareas de configuración.

En esta sección se asume que ha leído la documentación de implementación referente a la respuesta de llamadas en grupo (consulte [Planear la respuesta de llamadas en grupo en Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).

## Requisitos previos para la configuración de la respuesta de llamadas en grupo

La respuesta de llamadas en grupo exige los siguientes componentes:

  - Servicio de aplicaciones

  - Aplicación de estacionamiento de llamadas

Estos componentes se instalan automáticamente al implementar Telefonía IP empresarial.

## Derechos de usuario para la configuración de la respuesta de llamadas en grupo

Para la configuración de la respuesta de llamadas en grupo se usan las siguientes herramientas administrativas:

  - Shell de administración de Lync Server

  - Herramienta de kit de recursos SEFAUtil

Use Shell de administración de Lync Server para crear y administrar los grupos de respuesta de llamadas en la tabla de órbitas de Estacionamiento de llamadas. Use la herramienta de kit de recursos SEFAUtil para asignar un grupo de respuesta de llamadas y active o desactive la respuesta de llamadas en grupo para los usuarios.

Para configurar la respuesta de llamadas en grupo se necesita uno de los roles administrativos siguientes, según cuál sea la tarea:

  - **CsVoiceAdministrator:** con este rol de administrador se pueden crear, configurar y administrar todas las configuraciones y directivas de voz.

  - **CsUserAdministrator:** con este rol de administrador se puede activar la respuesta de llamadas en grupo para los usuarios. De igual modo, permite el acceso de vista de solo lectura a todas las configuraciones de voz.

  - **CsServerAdministrator:** con este rol de administrador se pueden administrar y supervisar servidores y servicios, así como solucionar problemas relacionados con ellos.

  - **CsAdministrator:** con este rol de administrador se pueden realizar todas las tareas de CsVoiceAdministrator, CsServerAdministrator y CsUserAdministrator.


> [!NOTE]
> Para más información sobre los derechos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planeación del control de acceso basado en roles en Lync Server 2013</A> en la documentación de planeación.



## Vea también

#### Conceptos

[Implementar la telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  

#### Otros recursos

[Planificar las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)

