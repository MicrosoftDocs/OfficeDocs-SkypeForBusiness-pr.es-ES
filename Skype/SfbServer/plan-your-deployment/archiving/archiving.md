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
ms.openlocfilehash: 87a408bd4decfcd4f1f0d1ca7806391ecb3900e8821031efec116d86a0847c3f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331132"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Planear el archivado en Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo planear el archivado en Skype Empresarial Server.
  
Las corporaciones y otras organizaciones están sujetas a un número creciente de reglamentaciones gubernamentales y del sector que requieren la retención de determinados tipos de comunicaciones. Si su organización tiene estos requisitos, puede usar el archivado en Skype Empresarial Server para archivar comunicaciones de mensajería instantánea (MI) y conferencias (reunión) para ayudar a admitir algunos de los requisitos de cumplimiento.
  
## <a name="archiving-components"></a>Componentes de archivado

Skype Empresarial Server los siguientes componentes de archivado:
  
- **Agentes de archivado** Los agentes de archivado (también conocidos como agentes de recopilación de datos unificados) se instalan y activan automáticamente en todos los Enterprise Edition grupo de servidores front-end y Standard Edition servidor. Aunque los agentes de archivado se activan automáticamente, no se capturan mensajes hasta que el archivado está habilitado y configurado correctamente. De forma predeterminada, el archivado está deshabilitado.
    
- **Almacenamiento de datos de archivado**. El almacenamiento de Skype Empresarial Server puede implementarse como bases de datos Skype Empresarial Server SQL Server o, si tiene una implementación Exchange, integrada con Exchange almacenamiento. 
    
El archivado también requiere almacenamiento de archivos, pero el archivado usa el mismo almacenamiento de archivos que los servidores front-end o Standard Edition servidor.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Determinar los requisitos de las organizaciones para el archivado

Para implementar el archivado, debe decidir cómo cumplir los requisitos de archivado de su organización mediante la determinación de lo siguiente:
  
- **Qué opción de almacenamiento se va a usar**. Puede implementar el almacenamiento de una de dos maneras o usar una combinación de ambas:
    
  - **Exchange almacenamiento.** Si tiene una implementación Exchange, puede integrar el archivado Skype Empresarial Server y Exchange para que los datos archivados Skype Empresarial Server y Exchange se almacenen juntos en Exchange. Si habilita la opción de integración de Microsoft Exchange, los buzones de usuario que se almacenan en el Exchange Server usan almacenamiento Exchange para los datos archivados, pero solo si los buzones se han puesto In-Place retención. De forma predeterminada, microsoft Exchange la integración no está habilitada.
    
  - **Skype Empresarial Server almacenamiento.** Si tiene usuarios que no están adosados en Exchange o que no han puesto sus buzones en retención de In-Place, o si no desea usar la integración de Microsoft Exchange para ninguno o todos los usuarios de la implementación, puede implementar bases de datos de archivado de Skype Empresarial Server mediante SQL Server.
    
- **Cuándo implementar el archivado**. Puede implementar el archivado como parte de la implementación Skype Empresarial Server implementación inicial o puede agregarlo a una implementación existente. Para usar Skype Empresarial Server almacenamiento de archivado (SQL Server base de datos), use el Generador de topologías para agregar las bases de datos a la topología y, a continuación, vuelva a publicar la topología. Si todos los usuarios se encuentran en Exchange y tienen sus buzones en retención In-Place, no es necesario actualizar la topología, sino que solo es necesario habilitar la integración de Microsoft Exchange para almacenar datos archivados en Exchange. 
    
- **Qué sitios y usuarios de la organización requieren archivado.** Puede configurar las opciones de archivado para toda la organización y, opcionalmente, para sitios, grupos de servidores, usuarios y grupos de usuarios específicos.
    
- **Qué contenido se debe archivar**. Tanto si especifica el archivado a nivel global como para sitios y usuarios específicos, en cada uno de estos niveles, especifique si desea habilitar los siguientes tipos de contenido: 
    
  - Mensajes instantáneos de punto a punto
    
  - Conferencias (reuniones), que son mensajes instantáneos con varios participantes
    
  - Contenido de conferencias, como contenido que se carga (por ejemplo, documentos de la reunión) y contenido relacionado con el evento (por ejemplo, los usuarios que se unen o abandonan el evento, la carga de recursos compartidos y cambios en la visibilidad)
    
  - Pizarras y sondeos los compartidos durante una conferencia
    
- **Qué contenido no se puede archivar**. No se pueden archivar los siguientes tipos de contenido: 
    
  - Transferencias de archivos de punto a punto
    
  - Audio y vídeo para conferencias y mensajes instantáneos de punto a punto
    
  - Escritorio y uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto
    
    Skype Empresarial Server tampoco archiva las conversaciones de chat persistente. Para archivar conversaciones de chat persistente, debe habilitar y configurar el servicio de cumplimiento, que es un componente que se puede implementar con el servidor de chat persistente. Para obtener más información, vea [Plan for Persistent Chat Server in Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams, o bien seguir usando Skype Empresarial Server 2015. 
    
- **Cuánto tiempo deben conservarse los materiales archivados.** La base de datos de archivado no está diseñada para la retención a largo plazo y Skype Empresarial Server no proporciona una solución de detección electrónica (búsqueda) para los datos archivados, por lo que los datos deben moverse a otro almacenamiento. Skype Empresarial Server proporciona una herramienta de exportación de sesión que puede usar para exportar datos archivados y que crea transcripciones de los datos archivados que se pueden buscar. 
    
     Para la directiva global y para cada sitio y directiva de usuario que cree, puede especificar cuándo se deben purgar los datos archivados y exportados. Para obtener más información acerca de la depuración de datos, vea [Manage purging of archived data in Skype Empresarial Server](../../manage/archiving/purging-of-archived-data.md). Para obtener más información acerca del uso de la herramienta de exportación de sesión, vea [Export archived data in Skype Empresarial Server](../../manage/archiving/export-archived-data.md).
    
- **Archivar o no las comunicaciones internas o externas**. Puede habilitar el archivado de las comunicaciones internas (comunicaciones entre usuarios internos), las comunicaciones externas (comunicaciones que incluyen al menos un usuario fuera de la red interna), o ambas. Puede especificar estas opciones para toda la organización o bien para grupos y sitios específicos. De forma predeterminada, no se habilita ninguna de estas opciones.
    
    > [!NOTE]
    > El control del archivado para las comunicaciones internas o externas solo está disponible para Skype Empresarial directiva. Para Exchange archivado integrado, las comunicaciones internas y externas se archivan o no. 
  
- **Si se va a implementar el modo crítico**. Si el archivado es un requisito para su organización, la configuración del modo crítico bloqueará las sesiones de mensajería instantánea y conferencia en caso de que se Skype Empresarial Server un error que impida el archivado. Por ejemplo: 
    
  - Un problema con el servicio Skype Empresarial Server de almacenamiento. En este caso, la mensajería instantánea se bloquea para los usuarios que están habilitados para el archivado.
    
  - Un recurso compartido de archivos no disponible o un problema con el servicio de almacenamiento. En este caso, todas las conferencias activas alojadas en el grupo de servidores en el momento del error se cambian al modo restringido y no se puede activar conferencias nuevas.
    
    Tanto el servicio de mensajería instantánea como de conferencias se recuperan automáticamente después de que se corrigen los errores.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Elegir opciones de configuración y implementación de archivado

El archivado se instala automáticamente en cada servidor front-end al implementar el servidor, pero el archivado no está habilitado hasta que se configura. La forma en que se configura el archivado viene determinada por la forma en que se implementa. Puede implementar el archivado de una de las siguientes maneras:
  
- Usar el almacenamiento Exchange Microsoft
    
- Usar Skype Empresarial Server almacenamiento
    
> [!NOTE]
> Si implementa las bases de datos de archivado de Skype Empresarial Server y habilita la integración de Microsoft Exchange, las directivas de Exchange invalidan las directivas de archivado de Skype Empresarial Server, pero solo para los usuarios que se encuentran en Exchange y han puesto sus buzones en retención In-Place. Skype Empresarial archivado depende de la directiva de retención Exchange In-Place Microsoft. 
  
Si implementa el archivado para un grupo de servidores front-end o un servidor Standard Edition, debe habilitarlo para todos los demás grupos de servidores front-end y Standard Edition servidores de la implementación. Si el archivado no está habilitado en el grupo donde se hospeda una conversación o reunión, es posible que no se archiven todos los datos de la conferencia. El archivado seguirá funcionando para los mensajes de mensajería instantánea, pero es posible que el contenido y los eventos de conferencia no se archiven.
  
> [!NOTE]
> Para habilitar la delegación de tareas administrativas mientras se mantienen los estándares de seguridad de la organización, Skype Empresarial Server el control de acceso basado en roles (RBAC). Con RBAC, se concede el privilegio administrativo asignando usuarios a roles administrativos predefinidos. Para configurar Skype Empresarial y configuraciones de archivado, el usuario debe estar asignado al rol CsArchivingAdministrator (a menos que la configuración se haga directamente en el servidor donde se implementa el archivado, en lugar de hacerlo de forma remota desde otro equipo). Para obtener una lista de los derechos de usuario, los permisos y los roles necesarios para la implementación de archivado, vea [Deploy archiving for Skype Empresarial Server](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Si usa la integración Exchange Microsoft, la configuración de Exchange directivas requiere los permisos y derechos de administrador adecuados. Para obtener más información, consulte Exchange documentación. 
  
### <a name="microsoft-exchange-storage"></a>Almacenamiento Exchange Microsoft

 Si elige la integración de Microsoft Exchange, usará las Exchange y las configuraciones para controlar el archivado de Skype Empresarial Server. Puede configurar la opción de integración Exchange Microsoft en el nivel global, el nivel de sitio y el nivel de grupo. Si la implementación incluye varios bosques, debe sincronizar la configuración entre Skype Empresarial Server y Exchange. Deberá determinar:
  
- Si archivar mensajería instantánea, conferencia o ambos
    
- Si se va a implementar el modo crítico, que bloquea las sesiones de mensajería instantánea y conferencia en caso de Skype Empresarial Server error 
    
- Selección de la opción de integración de Microsoft Exchange para usar Exchange para el almacenamiento de datos archivados
    
Para obtener información acerca de cómo configurar las Exchange In-Place de retención para admitir el archivado, consulte la Exchange del producto.
  
### <a name="skype-for-business-server-storage"></a>Skype Empresarial Server almacenamiento

Si elige el Skype Empresarial Server, use las directivas y configuraciones de archivado Skype Empresarial Server para controlar cómo se habilita e implementa el archivado. Skype Empresarial Server almacenamiento usa SQL Server bases de datos, por lo que deberá agregar las bases de datos de SQL Server adecuadas a la topología y, a continuación, configurar las directivas de archivado. 
  
### <a name="add-storage-databases-to-your-topology"></a>Agregar bases de datos de almacenamiento a la topología

Al agregar SQL Server de almacenamiento a la topología, puede optar por asociar las bases de datos de archivado con cualquiera de las siguientes opciones:
  
- Base de datos de supervisión
    
- Base de datos back-end de un grupo de servidores front-end de Enterprise Edition
    
> [!NOTE]
> El servidor que hospeda la base de datos de archivado puede hospedar otras bases de datos. Sin embargo, si piensa combinar la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede crecer mucho. Por este motivo, no se recomienda la combinación de la base de datos de archivado con la base de datos back-end. 
  
Si coloca la base de datos de archivado con la base de datos de supervisión, la base de datos back-end o ambas bases de datos, puede usar una sola instancia de SQL para cualquiera o todas las bases de datos, o puede usar una instancia SQL independiente para cada base de datos, con la siguiente limitación: cada instancia SQL puede contener solo una base de datos back-end, una sola base de datos de supervisión y una sola base de datos de archivado.
  
Para obtener más información acerca de la ubicación de todas las bases de datos y roles de servidor, vea [Topology Basics for Skype Empresarial Server](../../plan-your-deployment/topology-basics/topology-basics.md). Para obtener más información sobre cómo actualizar la topología para incluir bases de datos de almacenamiento, vea [Create and publish new topology in Skype Empresarial Server](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Determinar las opciones de archivado y las directivas de usuario

Deberá determinar:
  
- Si se habilita o deshabilita el archivado para comunicaciones internas y externas
    
- Si archivar mensajería instantánea, conferencia o ambos
    
- Si se va a implementar el modo crítico, que bloquea las sesiones de mensajería instantánea y conferencia en caso de Skype Empresarial Server error 
    
- Si se habilitan directivas para usuarios y grupos específicos
    
Skype Empresarial Server Las opciones de archivado se pueden especificar en los siguientes niveles. 
  
- **Opción de nivel global**. Esta es la configuración de archivado predeterminada y se aplica a toda la implementación. Se crea al implementar Skype Empresarial Server y, de forma predeterminada, deshabilita el archivado para comunicaciones internas y externas. No puede eliminar esta opción. Si elige la opción eliminar, la opción global se restablecerá a la configuración predeterminada.
    
- **Opciones de nivel de sitio**. Puede habilitar o deshabilitar el archivado para uno o varios sitios específicos mediante la creación y configuración de una opción de archivado de nivel de sitio para el sitio. Puede eliminar cualquier opción de archivado a nivel de sitio que cree. Una opción de archivado a nivel de sitio invalida la opción global, pero solo para el sitio especificado en la opción. 
    
    Por ejemplo, si habilita el archivado para comunicaciones internas y externas en la configuración global y crea una configuración de sitio en la que deshabilita el archivado para comunicaciones externas, solo se archivarán las comunicaciones internas para ese sitio. Por otro ejemplo, si habilita el archivado solo para mi en la configuración global y crea una configuración de sitio en la que habilita el archivado para mensajería instantánea y conferencia, las conferencias solo se archivarán para el sitio, no para el resto de la organización.
    
- **Opciones de nivel de grupo**. Puede especificar la configuración de archivado para uno o varios grupos de servidores específicos mediante la creación y configuración de una configuración de nivel de grupo para el grupo de servidores individual. Solo existe una configuración de archivado de nivel de grupo si la crea. Puede modificar y eliminar cualquier configuración de archivado de nivel de grupo. Una configuración de archivado de nivel de grupo invalida la configuración global y cualquier configuración de archivado de sitios que haya creado. 
    
    Por ejemplo, suponga que habilita el archivado para mi solo en la configuración global, después cree una configuración de nivel de sitio en la que habilite el archivado para mensajería instantánea y conferencia y, a continuación, cree una configuración de nivel de grupo en la que habilite el archivado solo para mensajería instantánea. Las comunicaciones se archivarán tanto para mensajería instantánea como para conferencias para todos los usuarios del sitio, excepto para los usuarios que se alomen en el grupo especificado en la configuración de nivel de grupo. Para todos los demás usuarios de la organización, el archivado solo se habilitaría para mensajería instantánea.
    
- **Directivas de archivado de usuarios**. Puede habilitar o deshabilitar el archivado para uno o varios usuarios y grupos específicos de usuarios mediante la creación, configuración y aplicación de una directiva de archivado de nivel de usuario para los usuarios y grupos de usuarios especificados. Puede eliminar cualquier directiva de archivado de nivel de usuario que cree y puede cambiar a qué usuarios y grupo de usuarios se aplica la directiva de archivado. Una directiva de archivado de nivel de usuario invalida la directiva global y las directivas de sitio, pero solo para los usuarios y grupos de usuarios a los que se aplica la directiva. 
    
    Por ejemplo, supongamos que deshabilita el archivado para comunicaciones internas y externas en la configuración global, cree una directiva de nivel de sitio en la que habilite el archivado para comunicaciones internas y externas y, a continuación, cree una directiva de nivel de usuario en la que deshabilite el archivado para comunicaciones externas. Las comunicaciones se archivarían tanto para comunicaciones externas como internas para todos los usuarios del sitio, excepto para los usuarios a los que aplica la directiva de nivel de usuario; para estos usuarios solo se archivarían las comunicaciones internas.
    
Para obtener más información sobre cómo configurar las configuraciones de archivado iniciales al implementar el archivado, vea [Deploy archiving for Skype Empresarial Server](../../deploy/deploy-archiving/deploy-archiving.md). Para obtener más información sobre cómo administrar el archivado después de la implementación, vea [Manage archiving in Skype Empresarial Server](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Herramientas de configuración de archivado

 La mayoría de las opciones de archivado se controlan mediante el panel Skype Empresarial Server control. Sin embargo, hay algunas opciones disponibles solo mediante el Shell Skype Empresarial Server administración. Estas opciones incluyen archivar mensajes duplicados y exportar datos archivados. Para obtener más información acerca del uso del Panel de control de Skype Empresarial Server y el Shell de administración de Skype Empresarial Server para administrar directivas de archivado, vea [Manage archiving in Skype Empresarial Server](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Acceder a datos archivados

El acceso a los datos archivados depende de dónde se almacenan los datos: 
  
- **Almacenamiento Exchange Microsoft**. Si elige la opción de integración Exchange, Skype Empresarial Server deposita el contenido de archivado en el almacén de Exchange para todos los usuarios que se encuentran en Exchange y que han puesto sus buzones en retención In-Place. Los datos archivados se almacenan en la carpeta elementos recuperables de los buzones de usuario, que  generalmente es invisible para los usuarios y solo los usuarios con un rol de administración de detección Exchange búsqueda. Exchange permite la búsqueda federada y la detección, junto con SharePoint, si se implementa. Para obtener más información sobre el almacenamiento, retención y detección de datos almacenados en Exchange, consulte la Exchange y SharePoint datos.
    
- **Skype Empresarial Server de archivado**. Si configura bases de datos de archivado de Skype Empresarial Server, Skype Empresarial Server deposita contenido de archivado en las bases de datos de archivado de Skype Empresarial Server para los usuarios que no están ubicados en Exchange y que no han puesto sus buzones en retención In-Place. Estos datos no pueden buscarse, pero se pueden exportar a formatos que se pueden buscar mediante otras herramientas. Para obtener más información acerca de la exportación de datos almacenados en bases de datos de archivado, vea [Export archived data in Skype Empresarial Server](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Más información

Para obtener más información acerca del archivado, consulte los temas siguientes:
  
- [Implementar el archivado para Skype Empresarial Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Administrar el archivado en Skype Empresarial Server](../../manage/archiving/archiving.md)
    
Para obtener más información sobre Skype Empresarial Server y Exchange trabajo en conjunto, vea [Plan to integrate Skype Empresarial and Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

