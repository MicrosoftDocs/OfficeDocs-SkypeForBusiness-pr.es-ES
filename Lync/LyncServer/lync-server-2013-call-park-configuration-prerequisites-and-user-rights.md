---
title: "Lync Server 2013: Requisitos del estacionamiento de llamadas y derechos de usuario"
TOCTitle: Requisitos previos de configuración del estacionamiento de llamadas y derechos de usuario
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48274712
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos previos de configuración del estacionamiento de llamadas y derechos de usuario en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-10_

Estacionamiento de llamadas es una característica de administración de llamadas que se instala de forma predeterminada al implementar Telefonía IP empresarial. En este tema se explica qué elementos deben existir para poder configurar Estacionamiento de llamadas, así como los derechos de usuario que se necesitan para llevar a cabo tareas de configuración.

> [!IMPORTANT]  
> No se realiza copia de seguridad de los archivos de música en espera personalizados para Aplicación de estacionamiento de llamadas como parte del proceso de recuperación ante desastres de Lync Server 2013 y los archivos se perderán si se dañan o se borran los archivos cargados al grupo de servidores. Conserve siempre una copia de seguridad independiente de los archivos de música en espera personalizados que ha cargado para Estacionamiento de llamadas.



A este respecto, se da por hecho que ya se ha leído la documentación de planeación sobre Estacionamiento de llamadas; para ello, vea [Planificar las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md).

## Requisitos previos de configuración de Estacionamiento de llamadas

Estacionamiento de llamadas requiere los siguientes componentes:

  - Servicio de aplicaciones

  - Aplicación de estacionamiento de llamadas

Estos componentes se instalan automáticamente al implementar Telefonía IP empresarial.

Si quiere que los autores de la llamada escuchen música cuando una llamada se estacione, también necesitará un archivo de música en espera. Cuando Telefonía IP empresarial se implementa, se instala automáticamente un archivo de música en espera predeterminado, que puede sustituir por su propio archivo de música en espera. Estacionamiento de llamadas usa el almacén de archivos para guardar el archivo de audio.

## Derechos de usuario para la configuración del Estacionamiento de llamadas

Puede usar las siguientes herramientas administrativas para configurar el Estacionamiento de llamadas:

  - Panel de control de Lync Server

  - Shell de administración de Lync Server

Estas herramientas pueden servir para configurar la tabla de órbitas del Estacionamiento de llamadas, así como para establecer otras configuraciones que Estacionamiento de llamadas usa.

Para configurar Estacionamiento de llamadas se requiere cualquiera de los siguientes roles administrativos (según cuál sea la tarea):

  - **CsVoiceAdministrator :** con este rol de administrador se pueden crear, configurar y administrar todas las configuraciones y directivas de voz.

  - **CsUserAdministrator :** con este rol de administrador se puede habilitar Estacionamiento de llamadas en la directiva de voz. De igual modo, permite el acceso de vista de solo lectura a todas las configuraciones de voz.

  - **CsServerAdministrator :** con este rol de administrador se pueden administrar y supervisar servidores y servicios, así como solucionar problemas relacionados con ellos.

  - **CsAdministrator :** con este rol de administrador se pueden realizar todas las tareas de CsVoiceAdministrator, CsServerAdministrator y CsUserAdministrator.


> [!NOTE]
> Para más información sobre los derechos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planeación del control de acceso basado en roles en Lync Server 2013</A> en la documentación de planeación.



## Vea también

#### Conceptos

[Implementar la telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  

#### Otros recursos

[Planificar las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)

