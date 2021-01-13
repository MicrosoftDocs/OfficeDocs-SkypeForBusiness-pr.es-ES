---
title: Planear el archivado en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Resumen: lea este tema para obtener información sobre cómo planear el archivado en Skype Empresarial Server.'
ms.openlocfilehash: b868555b0a79b1abdfd96e50cf88d6db9cdae2ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810150"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Planear el archivado en Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo planear el archivado en Skype Empresarial Server.
  
Las corporaciones y otras organizaciones están sujetas a un número creciente de reglamentaciones gubernamentales y del sector que requieren la retención de determinados tipos de comunicaciones. Si su organización tiene estos requisitos, puede usar el archivado en Skype Empresarial Server para archivar las comunicaciones de mensajería instantánea (MI) y conferencias (reunión) para ayudar a cumplir algunos de sus requisitos de cumplimiento.
  
## <a name="archiving-components"></a>Componentes de archivado

Skype Empresarial Server usa los siguientes componentes de archivado:
  
- **Agentes de archivado** Los agentes de archivado (también conocidos como agentes de recopilación de datos unificados) se instalan y activan automáticamente en cada grupo de servidores front-end Enterprise Edition y en el servidor Standard Edition. Aunque los agentes de archivado se activan automáticamente, no se capturan realmente mensajes hasta que el archivado está habilitado y configurado correctamente. De forma predeterminada, el archivado está deshabilitado.
    
- **Almacenamiento de datos de archivado**. El almacenamiento de datos de Skype Empresarial Server se puede implementar como bases de datos de Skype Empresarial Server SQL Server o, si tiene una implementación de Exchange, integrada con el almacenamiento de Exchange. 
    
El archivado también requiere almacenamiento de archivos, pero el archivado usa el mismo almacenamiento de archivos que los servidores front-end o el servidor Standard Edition.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Determinar los requisitos de archivado de las organizaciones

Para implementar el archivado, debe decidir cómo cumplir los requisitos de archivado de su organización mediante la determinación de lo siguiente:
  
- **La opción de almacenamiento que se va a usar.** Puede implementar el almacenamiento de una de estas dos maneras o usar una combinación de ambas:
    
  - **Almacenamiento de Exchange.** Si tiene una implementación de Exchange, puede integrar Skype Empresarial Server y archivado de Exchange para que los datos archivados de Skype Empresarial Server y Exchange se almacenen juntos en Exchange. Si habilita la opción de integración de Microsoft Exchange, los buzones de usuario que están en la Exchange Server usan el almacenamiento de Exchange para los datos archivados, pero solo si los buzones se han puesto en In-Place Retención. De forma predeterminada, la integración de Microsoft Exchange no está habilitada.
    
  - **Almacenamiento de Skype Empresarial Server.** Si tiene usuarios que no están en Exchange o que no han puesto sus buzones en una retención In-Place, o si no desea usar la integración de Microsoft Exchange para ninguno o todos los usuarios de la implementación, puede implementar bases de datos de archivado de Skype Empresarial Server mediante SQL Server.
    
- **Cuándo implementar el archivado.** Puede implementar el archivado como parte de la implementación inicial de Skype Empresarial Server o puede agregarlo a una implementación existente. Para usar el almacenamiento de archivado de Skype Empresarial Server (bases de datos de SQL Server), use el Generador de topologías para agregar las bases de datos a la topología y, a continuación, publique la topología de nuevo. Si todos los usuarios están en Exchange y tienen sus buzones en retención In-Place, no es necesario actualizar la topología, sino que solo necesita habilitar la integración de Microsoft Exchange para almacenar datos archivados en Exchange. 
    
- **Qué sitios y usuarios de la organización requieren archivado.** Puede configurar las opciones de archivado para toda la organización y, opcionalmente, para sitios, grupos, usuarios y grupos de usuarios específicos.
    
- **Qué contenido se debe archivar.** Tanto si especifica el archivado en el nivel global como para sitios y usuarios específicos, en cada uno de estos niveles, especifique si desea habilitar los siguientes tipos de contenido: 
    
  - Mensajes instantáneos de punto a punto
    
  - Conferencias (reuniones), que son mensajes instantáneos con varios participantes
    
  - Contenido de conferencias, como contenido que se carga (por ejemplo, documentos de la reunión) y contenido relacionado con el evento (por ejemplo, los usuarios que se unen o abandonan el evento, la carga de recursos compartidos y cambios en la visibilidad)
    
  - Pizarras y sondeos los compartidos durante una conferencia
    
- **Qué contenido no se puede archivar.** No se pueden archivar los siguientes tipos de contenido: 
    
  - Transferencias de archivos de punto a punto
    
  - Audio y vídeo para conferencias y mensajes instantáneos de punto a punto
    
  - Escritorio y uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto
    
    Skype Empresarial Server tampoco archiva las conversaciones de chat persistente. Para archivar conversaciones de chat persistente, debe habilitar y configurar el servicio de cumplimiento, que es un componente que se puede implementar con el servidor de chat persistente. Para obtener más información, consulte [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 
    
- **Cuánto tiempo deben conservarse los materiales archivados.** La base de datos de archivado no está pensada para la retención a largo plazo y Skype Empresarial Server no proporciona una solución de detección electrónica (búsqueda) para los datos archivados, por lo que los datos deben moverse a otro almacenamiento. Skype Empresarial Server proporciona una herramienta de exportación de sesión que puede usar para exportar datos archivados y que crea transcripciones que pueden buscarse de los datos archivados. 
    
     Para la directiva global y para cada directiva de sitio y usuario que cree, puede especificar cuándo purgar los datos archivados y exportados. Para obtener más información acerca de la depuración de datos, consulte Administrar la purga de datos archivados [en Skype Empresarial Server.](../../manage/archiving/purging-of-archived-data.md) Para obtener más información acerca del uso de la herramienta de exportación de sesión, vea Exportar datos [archivados en Skype Empresarial Server.](../../manage/archiving/export-archived-data.md)
    
- **Archivar o no las comunicaciones internas o externas**. Puede habilitar el archivado de las comunicaciones internas (comunicaciones entre usuarios internos), las comunicaciones externas (comunicaciones que incluyen al menos un usuario fuera de la red interna), o ambas. Puede especificar estas opciones para toda la organización o bien para grupos y sitios específicos. De forma predeterminada, no se habilita ninguna de estas opciones.
    
    > [!NOTE]
    > El control del archivado para las comunicaciones internas o externas solo está disponible para la directiva de Skype Empresarial. Para el archivado integrado en Exchange, las comunicaciones internas y externas se archivan o no. 
  
- **Si se va a implementar el modo crítico.** Si el archivado es un requisito para su organización, la configuración del modo crítico bloqueará las sesiones de mensajería instantánea y conferencia en caso de un error de Skype Empresarial Server que impediría el archivado. Por ejemplo: 
    
  - Un problema con el servicio de almacenamiento de Skype Empresarial Server. En este caso, la mensajería instantánea se bloquea para los usuarios que están habilitados para el archivado.
    
  - Un recurso compartido de archivos no disponible o un problema con el servicio de almacenamiento. En este caso, todas las conferencias activas alojadas en el grupo de servidores en el momento del error se cambian al modo restringido y no se puede activar conferencias nuevas.
    
    Tanto el servicio de mensajería instantánea como de conferencias se recuperan automáticamente después de que se corrigen los errores.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Elegir opciones de implementación y configuración de archivado

El archivado se instala automáticamente en cada servidor front-end cuando se implementa el servidor, pero el archivado no está habilitado hasta que se configura. La forma en que se configura el archivado depende de cómo se implemente. Puede implementar el archivado de una de las siguientes maneras:
  
- Usar el almacenamiento de Microsoft Exchange
    
- Usar el almacenamiento de Skype Empresarial Server
    
> [!NOTE]
> Si implementa las bases de datos de archivado de Skype Empresarial Server y habilita la integración de Microsoft Exchange, las directivas de Exchange invalidan las directivas de archivado de Skype Empresarial Server, pero solo para los usuarios que están en Exchange y que tienen sus buzones en retención In-Place local. El archivado de Skype Empresarial depende de la directiva de retención In-Place de Microsoft Exchange. 
  
Si implementa el archivado para un grupo de servidores front-end o un servidor Standard Edition, debe habilitarlo para todos los demás grupos de servidores front-end y servidores Standard Edition de la implementación. Si el archivado no está habilitado en el grupo de servidores donde se hospeda una conversación o reunión, es posible que no se archiven todos los datos de conferencia. El archivado seguirá funcionando para los mensajes de mensajería instantánea, pero es posible que el contenido y los eventos de conferencia no se archiven.
  
> [!NOTE]
> Para habilitar la delegación de tareas administrativas mientras se mantienen los estándares de seguridad de su organización, Skype Empresarial Server usa el control de acceso basado en roles (RBAC). Con RBAC, se concede el privilegio administrativo asignando usuarios a roles administrativos predefinidos. Para configurar las directivas y configuraciones de archivado de Skype Empresarial, el usuario debe estar asignado al rol CsArchivingAdministrator (a menos que la configuración se haga directamente en el servidor donde se implementa el archivado, en lugar de hacerlo de forma remota desde otro equipo). Para obtener una lista de los derechos de usuario, permisos y roles necesarios para la implementación de archivado, consulte [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Si usa la integración de Microsoft Exchange, la configuración de directivas de Exchange requiere permisos y derechos de administrador adecuados. Para obtener más información, consulte la documentación de Exchange. 
  
### <a name="microsoft-exchange-storage"></a>Almacenamiento de Microsoft Exchange

 Si elige la integración de Microsoft Exchange, usará las directivas y configuraciones de Exchange para controlar el archivado de Skype Empresarial Server. Puede configurar la opción de integración de Microsoft Exchange en el nivel global, de sitio y de grupo. Si la implementación incluye varios bosques, debe sincronizar la configuración entre Skype Empresarial Server y Exchange. Deberá determinar lo siguiente:
  
- Si se va a archivar la mensajería instantánea, las conferencias o ambos
    
- Si se va a implementar el modo crítico, que bloquea las sesiones de mensajería instantánea y conferencia en caso de un error de Skype Empresarial Server 
    
- Selección de la opción de integración de Microsoft Exchange para usar Exchange para almacenar datos archivados
    
Para obtener información sobre cómo configurar las directivas y las opciones de retención In-Place Exchange para admitir el archivado, consulte la documentación del producto de Exchange.
  
### <a name="skype-for-business-server-storage"></a>Almacenamiento de Skype Empresarial Server

Si elige el almacenamiento de Skype Empresarial Server, usará las directivas y configuraciones de archivado de Skype Empresarial Server para controlar cómo se habilita e implementa el archivado. El almacenamiento de Skype Empresarial Server usa SQL Server bases de datos, por lo que deberá agregar las bases de datos de SQL Server adecuadas a la topología y, a continuación, configurar las directivas de archivado. 
  
### <a name="add-storage-databases-to-your-topology"></a>Agregar bases de datos de almacenamiento a la topología

Al agregar SQL Server bases de datos de almacenamiento a la topología, puede optar por colocar las bases de datos de archivado con cualquiera de las siguientes opciones:
  
- Base de datos de supervisión
    
- Base de datos back-end de un grupo de servidores front-end de Enterprise Edition
    
> [!NOTE]
> El servidor que hospeda la base de datos de archivado puede hospedar otras bases de datos. Sin embargo, si piensa combinar la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede crecer mucho. Por este motivo, no se recomienda la combinación de la base de datos de archivado con la base de datos back-end. 
  
Si coloca la base de datos de archivado con la base de datos de supervisión, la base de datos back-end o ambas bases de datos, puede usar una sola instancia de SQL para cualquiera o todas las bases de datos, o puede usar una instancia SQL independiente para cada base de datos, con la siguiente limitación: cada instancia SQL puede contener una sola base de datos back-end, una sola base de datos de supervisión y una sola base de datos de archivado.
  
Para obtener más información sobre la colocación de todas las bases de datos y roles de servidor, consulte [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md). Para obtener más información sobre cómo actualizar la topología para incluir bases de datos de almacenamiento, consulte Crear y publicar una nueva [topología en Skype Empresarial Server.](../../deploy/install/create-and-publish-new-topology.md)
  
### <a name="determine-archiving-options-and-user-policies"></a>Determinación de las opciones de archivado y las directivas de usuario

Deberá determinar lo siguiente:
  
- Si se habilita o deshabilita el archivado para comunicaciones internas y externas
    
- Si se va a archivar la mensajería instantánea, las conferencias o ambos
    
- Si se va a implementar el modo crítico, que bloquea las sesiones de mensajería instantánea y conferencia en caso de un error de Skype Empresarial Server 
    
- Si se habilitan directivas para usuarios y grupos específicos
    
Las opciones de archivado de Skype Empresarial Server se pueden especificar en los siguientes niveles. 
  
- **Opción de nivel global**. Esta es la configuración de archivado predeterminada y se aplica a toda la implementación. Se crea al implementar Skype Empresarial Server y, de forma predeterminada, deshabilita el archivado para las comunicaciones internas y externas. No puede eliminar esta opción. Si elige la opción de eliminación, la opción global se restablece a la configuración predeterminada.
    
- **Opciones de nivel de sitio.** Puede habilitar o deshabilitar el archivado para uno o más sitios específicos mediante la creación y configuración de una opción de archivado de nivel de sitio para el sitio. Puede eliminar cualquier opción de archivado de nivel de sitio que cree. Una opción de archivado de nivel de sitio reemplaza la opción global, pero solo para el sitio especificado en la opción. 
    
    Por ejemplo, si habilita el archivado para comunicaciones internas y externas en la configuración global y crea una configuración de sitio en la que deshabilita el archivado para las comunicaciones externas, solo se archivarán las comunicaciones internas para ese sitio. Por otro ejemplo, si habilita el archivado solo para mensajería instantánea en la configuración global y crea una configuración de sitio en la que habilita el archivado para mensajería instantánea y conferencias, las conferencias solo se archivarán para el sitio, no para el resto de la organización.
    
- **Opciones de nivel de grupo** de servidores. Puede especificar la configuración de archivado para uno o más grupos de servidores específicos mediante la creación y configuración de una configuración de nivel de grupo para el grupo de servidores individual. Solo existe una configuración de archivado de nivel de grupo si la crea. Puede modificar y eliminar cualquier configuración de archivado de nivel de grupo. Una configuración de archivado de nivel de grupo reemplaza la configuración global y cualquier configuración de archivado de sitio que haya creado. 
    
    Por ejemplo, suponga que habilita el archivado para mensajería instantánea solo en la configuración global, cree una configuración de nivel de sitio en la que habilite el archivado para mensajería instantánea y conferencias y, a continuación, cree una configuración de nivel de grupo en la que habilite el archivado solo para mensajería instantánea. Las comunicaciones se archivarían tanto para mensajería instantánea como para conferencias para todos los usuarios del sitio, excepto para los usuarios del grupo especificado en la configuración de nivel de grupo. Para todos los demás usuarios de la organización, el archivado solo se habilitaría para mensajería instantánea.
    
- **Directivas de archivado de usuarios.** Puede habilitar o deshabilitar el archivado para uno o varios usuarios y grupos de usuarios específicos mediante la creación, configuración y aplicación de una directiva de archivado de nivel de usuario para los usuarios y grupos de usuarios especificados. Puede eliminar cualquier directiva de archivado de nivel de usuario que cree y puede cambiar a qué usuarios y grupos de usuarios se aplica la directiva de archivado. Una directiva de archivado de nivel de usuario reemplaza la directiva global y cualquier directiva de sitio, pero solo para los usuarios y grupos de usuarios a los que se aplica la directiva. 
    
    Por ejemplo, supongamos que deshabilita el archivado para las comunicaciones internas y externas en la configuración global, crea una directiva de nivel de sitio en la que habilita el archivado para las comunicaciones internas y externas y, a continuación, crea una directiva de nivel de usuario en la que deshabilita el archivado para las comunicaciones externas. Las comunicaciones se archivarían tanto para las comunicaciones internas como externas para todos los usuarios del sitio excepto para los usuarios a los que se aplica la directiva de nivel de usuario; para estos usuarios solo se archivarían las comunicaciones internas.
    
Para obtener más información sobre cómo configurar las configuraciones de archivado iniciales al implementar el archivado, consulte Implementar el [archivado para Skype Empresarial Server.](../../deploy/deploy-archiving/deploy-archiving.md) Para obtener más información sobre cómo administrar el archivado después de la implementación, consulte [Administrar el archivado en Skype Empresarial Server.](../../manage/archiving/archiving.md) 
  
## <a name="archiving-configuration-tools"></a>Herramientas de configuración de archivado

 La mayoría de las opciones de archivado se controlan mediante el Panel de control de Skype Empresarial Server. Sin embargo, hay algunas opciones disponibles solo mediante el Shell de administración de Skype Empresarial Server. Estas opciones incluyen el archivado de mensajes duplicados y la exportación de datos archivados. Para obtener más información sobre cómo usar el Panel de control de Skype Empresarial Server y el Shell de administración de Skype Empresarial Server para administrar directivas de archivado, consulte Administrar el archivado [en Skype Empresarial Server.](../../manage/archiving/archiving.md)
  
## <a name="access-archived-data"></a>Obtener acceso a datos archivados

El acceso a los datos archivados depende de dónde se almacenan los datos: 
  
- **Almacenamiento de Microsoft Exchange**. Si elige la opción de integración de Exchange, Skype Empresarial Server deposita el contenido de archivado en el almacén de Exchange para todos los usuarios que están en Exchange y que han puesto sus buzones en In-Place Retención. Los datos archivados se almacenan en la carpeta elementos recuperables de los buzones de usuario, que generalmente es invisible para los usuarios y solo pueden buscar los usuarios con un rol de administración de detección **de** Exchange. Exchange permite la búsqueda federada y la detección, junto con SharePoint, si se implementa. Para obtener más información sobre el almacenamiento, la retención y la detección de datos almacenados en Exchange, vea la documentación de Exchange y SharePoint.
    
- **Almacenamiento de archivado de Skype Empresarial Server.** Si configura bases de datos de archivado de Skype Empresarial Server, Skype Empresarial Server deposita contenido de archivado en las bases de datos de archivado de Skype Empresarial Server para los usuarios que no están ubicados en Exchange y que no han puesto sus buzones en In-Place Retención. Estos datos no pueden buscarse, pero se pueden exportar a formatos que se pueden buscar mediante otras herramientas. Para obtener más información sobre cómo exportar datos almacenados en bases de datos de archivado, consulte Exportar datos [archivados en Skype Empresarial Server.](../../manage/archiving/export-archived-data.md)
    
## <a name="for-more-information"></a>Más información

Para obtener más información acerca del archivado, consulte los siguientes temas:
  
- [Implementar el archivado para Skype Empresarial Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Administrar el archivado en Skype Empresarial Server](../../manage/archiving/archiving.md)
    
Para obtener más información sobre cómo Skype Empresarial Server y Exchange funcionan juntos, vea [Plan para integrar Skype Empresarial y Exchange.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
  

