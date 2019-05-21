---
title: Planear el archivado en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Resumen: Lea este tema para obtener información sobre cómo planear el archivado en Skype empresarial Server.'
ms.openlocfilehash: 4bbe6b5bd8eb9e5e56bfdea6f8a4187a6d14b231
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277604"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Planear el archivado en Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo planear el archivado en Skype empresarial Server.
  
Las corporaciones y otras organizaciones están sujetas a una creciente cantidad de reglamentaciones gubernamentales y del sector que requieren la retención de determinados tipos de comunicaciones. Si su organización tiene estos requisitos, puede usar el archivado en Skype empresarial Server para archivar las comunicaciones de mensajería instantánea (mi) y Conferencia (reunión) para ayudar a satisfacer algunos de sus requisitos de cumplimiento.
  
## <a name="archiving-components"></a>Componentes del archivado

Skype empresarial Server usa los siguientes componentes de archivado:
  
- **Agentes de archivado**. Los agentes de archivado (también llamados agentes unificados de recolección de datos) se instalan y activan automáticamente en cada grupo de servidores front-end Enterprise Edition y en el servidor Standard Edition. Aunque los agentes de archivado se activan automáticamente, no se capturan realmente mensajes hasta que se habilite y configure correctamente el archivado. De manera predeterminada, el archivado se encuentra deshabilitado.
    
- **Almacenamiento de datos de archivado**. El almacenamiento de datos de Skype empresarial Server se puede implementar como bases de datos de SQL Server de Skype empresarial Server, o bien, si tiene una implementación de Exchange, está integrada en el almacenamiento de Exchange. 
    
El archivado también requiere almacenamiento de archivos, pero el archivado usa el mismo almacenamiento de archivos que los servidores front-end o que el servidor Standard Edition.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Determinar los requisitos para el archivado de la organización

Para implementar el archivado, debe decidir cómo cumplir los requisitos de su organización para el archivado determinando lo siguiente:
  
- **Qué opción de almacenamiento usar**. Puede implementar el almacenamiento en una de las dos maneras o usar una combinación de ambas:
    
  - **Almacenamiento de Exchange.** Si tiene una implementación de Exchange, puede integrar el archivado de Skype empresarial Server y Exchange para que sus datos archivados de Skype empresarial Server y Exchange se almacenen conjuntamente en Exchange. Si habilita la opción de integración de Microsoft Exchange, los buzones de usuario alojados en el servidor de Exchange usan el almacenamiento de Exchange para los datos archivados, pero solo si los buzones se han colocado en una conservación local. De forma predeterminada, la integración de Microsoft Exchange no está habilitada.
    
  - **Almacenamiento de Skype empresarial Server.** Si hay usuarios que no estén alojados en Exchange o que no hayan puesto sus buzones en conservación local, o si no desea usar la integración de Microsoft Exchange para ninguno o todos los usuarios de su implementación, puede implementar bases de datos de archivo de Skype empresarial Server usando S Servidor de QL.
    
- **Cuándo implementar el archivado**. Puede implementar el archivado como parte de su implementación inicial de Skype empresarial Server, o bien puede agregarlo a una implementación existente. Para usar el almacenamiento de archivado de Skype empresarial Server (bases de datos de SQL Server), use el generador de topología para agregar las bases de datos a la topología y, a continuación, vuelva a publicar la topología. Si todos los usuarios están alojados en Exchange y sus buzones se colocan en conservación local, no tiene que actualizar su topología, pero solo necesita habilitar la integración de Microsoft Exchange para almacenar datos archivados en Exchange. 
    
- **Qué sitios y usuarios en la organización necesitan el archivado**. Puede establecer la configuración de archivado para toda la organización y, opcionalmente, para sitios, grupos, usuarios y grupos de usuarios específicos.
    
- **Qué contenido se tiene que archivar**. Ya sea si especifica el archivado de forma global o para usuarios y sitios específicos, en cada uno de estos ámbitos, especifique si habilitará los siguientes tipos de contenido: 
    
  - Mensajes instantáneos de punto a punto
    
  - Conferencias (reuniones), que son mensajes instantáneos con varios participantes
    
  - Contenido de conferencias, como contenido que se carga (por ejemplo, documentos de la reunión) y contenido relacionado con el evento (por ejemplo, los usuarios que se unen o abandonan el evento, la carga de recursos compartidos y los cambios en la visibilidad)
    
  - Pizarras y sondeos compartidos durante una conferencia
    
- **Qué contenido no se puede archivar**. Los siguientes tipos de contenido no se pueden archivar: 
    
  - Transferencias de archivos de punto a punto
    
  - Audio o vídeo para conferencias y mensajes instantáneos de punto a punto
    
  - Escritorio y uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto
    
    Skype empresarial Server tampoco archiva conversaciones de chat persistentes. Para archivar conversaciones de chat persistentes, debe habilitar y configurar el servicio de cumplimiento, que es un componente que se puede implementar con el servidor de chat persistente. Para obtener más información, vea [planear el servidor de chat persistente en Skype empresarial server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte Cómo desplazarse [de Skype empresarial a Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015. 
    
- **Cuánto tiempo es preciso conservar los materiales archivados**. La base de datos de archivado no está pensada para la retención a largo plazo, y Skype empresarial Server no proporciona una solución de detección electrónica (búsqueda) para los datos archivados, por lo que es necesario mover los datos a otro almacenamiento. Skype empresarial Server proporciona una herramienta de exportación de sesión que puede usar para exportar datos archivados y que crea transcripciones que permiten búsquedas de los datos archivados. 
    
     Para la directiva global y para cada sitio y Directiva de usuario que cree, puede especificar Cuándo purgar los datos archivados y los que se han exportado. Para obtener más información sobre cómo purgar datos, vea [administrar la purga de datos archivados en Skype empresarial Server](../../manage/archiving/purging-of-archived-data.md). Para obtener más información sobre el uso de la herramienta de exportación de sesiones, consulte [exportar datos archivados en Skype empresarial Server](../../manage/archiving/export-archived-data.md).
    
- **Si archivar las comunicaciones internas o externas**. Puede habilitar el archivado de las comunicaciones internas (comunicaciones entre usuarios internos), las comunicaciones externas (comunicaciones que incluyen al menos un usuario fuera de la red interna), o ambas. Puede especificar estas opciones para toda la organización, o bien para grupos y sitios específicos. De forma predeterminada, no se habilita ninguna de estas opciones.
    
    > [!NOTE]
    > Controlar el archivado para las comunicaciones internas o externas solo está disponible para las directivas de Skype empresarial. Para el archivado integrado de Exchange, tanto las comunicaciones internas como las externas se archivan o no se archivan. 
  
- **Si implementar el modo crítico**. Si el archivado es un requisito para su organización, la configuración del modo crítico bloqueará las sesiones de mensajería instantánea y de conferencias en el caso de que se produzca un error de Skype empresarial Server que impida el archivado. Por ejemplo: 
    
  - Un problema con el servicio de almacenamiento de Skype empresarial Server. En este caso, la mensajería instantánea (MI) se bloquea para los usuarios que están habilitados para el archivado.
    
  - Un recurso compartido de archivo no disponible o un problema con el servicio de almacenamiento. En este caso, todas las conferencias activas alojadas en el grupo de servidores en el momento del error se cambian al modo restringido y no se puede activar conferencias nuevas.
    
    Tanto la mensajería instantánea como las conferencias se recuperan automáticamente después de que se corrigen los errores.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Seleccionar las opciones de configuración y la implementación del archivado

El archivado se instala automáticamente en cada servidor front-end al implementar el servidor, pero el archivado no está habilitado hasta que se configura. La manera de configurarlo depende de la forma de implementar el archivado. Puede implementar el archivado de una de las siguientes maneras:
  
- Usar el almacenamiento de Microsoft Exchange
    
- Usar el almacenamiento de Skype empresarial Server
    
> [!NOTE]
> Si implementa las bases de datos de archivado de Skype empresarial y habilita la integración de Microsoft Exchange, las directivas de Exchange invalidan las directivas de archivado de Skype empresarial Server, pero solo para los usuarios alojados en Exchange y en los que se han colocado sus buzones Conservación local. El archivado de Skype empresarial depende de la Directiva de retención local de Microsoft Exchange. 
  
Si implementa el archivado para un grupo de servidores front-end o un servidor Standard Edition, debe habilitarlo para todos los demás grupos front-end y servidores Standard Edition de su implementación. Si el archivado no está habilitado en el grupo de servidores en el que se hospeda una conversación o una reunión, puede que no se puedan archivar todos los datos de la conferencia. El archivado seguirá funcionando para todos los mensajes de la mensajería instantánea (MI), pero posiblemente no se archiven los eventos y el contenido de las conferencias.
  
> [!NOTE]
> Para habilitar la delegación de tareas administrativas a la vez que se mantienen los estándares de seguridad de su organización, Skype empresarial Server usa control de acceso basado en roles (RBAC). Con RBAC, se concede el privilegio administrativo al asignar a los usuarios roles administrativos predefinidos. Para configurar las directivas y configuraciones de archivo de Skype empresarial, el usuario debe tener asignado el rol CsArchivingAdministrator (a menos que la configuración se haya realizado directamente en el servidor donde se haya implementado el archivado, en lugar de hacerlo de forma remota desde otro equipo). ). Para obtener una lista de los derechos de usuario, los permisos y los roles necesarios para la implementación de archivado, consulte [implementar el archivado de Skype empresarial Server](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Si utiliza la integración de Microsoft Exchange, la configuración de las directivas de Exchange requiere permisos y derechos de administrador apropiados. Para obtener más información, consulte la documentación de Exchange. 
  
### <a name="microsoft-exchange-storage"></a>Almacenamiento de Microsoft Exchange

 Si elige la integración de Microsoft Exchange, utilizará las directivas y configuraciones de Exchange para controlar el archivado de Skype empresarial Server. Puede configurar la opción de integración de Microsoft Exchange en el nivel global, en el nivel de sitio y en el nivel de grupo. Si su implementación incluye varios bosques, debe sincronizar la configuración entre Skype empresarial Server y Exchange. Tendrá que determinar lo siguiente:
  
- Si archivar la mensajería instantánea (MI), las conferencias o ambas
    
- Si se debe implementar el modo crítico, que bloquea las sesiones de mensajería instantánea y de conferencia en caso de que se produzca un error de Skype empresarial Server 
    
- Selección de la opción de integración de Microsoft Exchange para usar Exchange para el almacenamiento de datos archivados
    
Para obtener información sobre cómo configurar las directivas y la configuración de retención local de Exchange para admitir el archivado, consulte la documentación del producto de Exchange.
  
### <a name="skype-for-business-server-storage"></a>Almacenamiento de Skype Empresarial Server

Si elige el almacenamiento de Skype empresarial Server, use las directivas y configuraciones de archivado de Skype empresarial Server para controlar cómo se habilita y se implementa el archivado. El almacenamiento de Skype empresarial Server usa bases de datos de SQL Server, por lo que tendrá que agregar las bases de datos de SQL Server apropiadas a su topología y, a continuación, configurar las directivas de archivado. 
  
### <a name="add-storage-databases-to-your-topology"></a>Agregar bases de datos de almacenamiento a la topología

Al agregar bases de datos de almacenamiento de SQL Server a su topología, puede optar por Collocate las bases de datos de archivado con cualquiera de los siguientes:
  
- Base de datos de supervisión
    
- Base de datos back-end de un grupo de servidores front-end Enterprise Edition
    
> [!NOTE]
> El servidor que hospeda la base de datos de archivado puede hospedar otras bases de datos. Pero, si piensa combinar la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede crecer mucho. Por este motivo, no recomendamos la combinación de la base de datos de archivado con la base de datos back-end. 
  
Si Collocate la base de datos de archivado con la base de datos de supervisión, la base de datos back-end o ambas bases de datos, puede usar una única instancia de SQL para cualquiera de las bases de datos o todas ellas, o bien, puede usar una instancia SQL independiente para cada base de datos, con lo siguiente: limitación: cada instancia de SQL puede contener una única base de datos back-end, una única base de datos de supervisión y una única base de datos de archivado.
  
Para obtener más información sobre collocation de todos los roles de servidor y bases de datos, consulte [aspectos básicos de la topología de Skype empresarial Server](../../plan-your-deployment/topology-basics/topology-basics.md). Para obtener información detallada sobre cómo actualizar su topología para incluir bases de datos de almacenamiento, consulte [crear y publicar una nueva topología en Skype empresarial Server](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Determinar las opciones de archivado y las directivas de usuario

Es preciso que determine lo siguiente:
  
- Si habilitar (o deshabilitar) el archivado para las comunicaciones internas y externas
    
- Si archivar la mensajería instantánea (MI), las conferencias o ambas
    
- Si se debe implementar el modo crítico, que bloquea las sesiones de mensajería instantánea y de conferencia en caso de que se produzca un error de Skype empresarial Server 
    
- Si habilitar las directivas para usuarios y grupos específicos
    
Las opciones de archivado de Skype empresarial Server se pueden especificar en los siguientes niveles. 
  
- **Opción de ámbito global**. Esta es la configuración de archivado predeterminada y se aplica a toda la implementación. Se crea al implementar Skype empresarial Server y, de forma predeterminada, deshabilita el archivado para las comunicaciones internas y externas. Esta opción no se puede eliminar. Si elige la opción de eliminarla, la opción global se restablece a la configuración predeterminada.
    
- **Opciones en el ámbito de sitio**. Puede habilitar o deshabilitar el archivado para uno o más sitios específicos al crear y configurar una opción de archivado para el sitio. Todas las opciones de archivado para el sitio que cree se pueden eliminar. Una opción de archivado para el sitio reemplaza la opción global, pero solo para el sitio especificado en la opción. 
    
    Por ejemplo, si habilita el archivado para las comunicaciones internas y externas en la configuración global y crea una configuración de sitio en la que deshabilita el archivado para las comunicaciones externas, solo se archivarán las comunicaciones internas para ese sitio. Otro ejemplo sería el siguiente: si habilita el archivado solo para la mensajería instantánea (MI) en la configuración global y crea una configuración de sitio en la que habilita el archivado tanto para la mensajería instantánea (MI) como para las conferencias, solo se archivarán las conferencias para el sitio, y no para el resto de la organización.
    
- **Opciones en el ámbito de grupo**. Puede especificar la configuración de archivado para uno o más grupos específicos al crear y establecer una configuración para el grupo individual. Una configuración de archivado para un grupo solo existe si se la crea. Puede modificar y eliminar cualquier configuración de archivado para el grupo. Una configuración de archivado de grupo reemplaza la configuración global y cualquier configuración de archivado que haya creado. 
    
    Por ejemplo, supongamos que habilita el archivado para mi solo en su configuración global y, a continuación, crea una configuración de nivel de sitio en la que habilitar el archivado para mensajería instantánea y conferencias y, a continuación, crear una configuración de nivel de grupo en la que habilitar el archivado para mensajería instantánea . Las comunicaciones se archivarán para mensajería instantánea y conferencias para todos los usuarios del sitio, excepto los usuarios alojados en el grupo especificado en la configuración de nivel de grupo. Para el resto de los usuarios de su organización, el archivado se habilitará solo para mensajería instantánea.
    
- **Directivas de archivado de usuario**. Puede habilitar o deshabilitar el archivado para uno o más usuarios y grupos específicos al crear, configurar y aplicar una directiva de archivado de usuario para usuarios y grupos de usuarios específicos. Puede eliminar cualquier directiva de archivado de usuario que cree y puede cambiar a qué usuarios y a qué grupo de usuarios se aplica la directiva. Una directiva de archivado de usuario reemplaza la directiva global y todas las directivas de sitio, pero solo para los usuarios y los grupos de usuarios a quienes se aplique la política. 
    
    Por ejemplo, supongamos que deshabilita el archivado de las comunicaciones internas y externas en su configuración global, crea una directiva de nivel de sitio en la que habilitar el archivado para las comunicaciones internas y externas y, a continuación, crea una directiva de nivel de usuario en la que usted deshabilitar el archivado de comunicaciones externas. Las comunicaciones se archivarán para las comunicaciones externas e internas de todos los usuarios del sitio, excepto para los usuarios a los que usted aplica la Directiva de nivel de usuario, para estos usuarios solo se archivarían las comunicaciones internas.
    
Para obtener más información sobre cómo configurar las configuraciones de archivado iniciales al implementar el archivado, consulte [implementar el archivado de Skype empresarial Server](../../deploy/deploy-archiving/deploy-archiving.md). Para obtener más información sobre cómo administrar el archivado después de la implementación, consulte [administrar el archivado en Skype empresarial Server](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Herramientas de configuración del archivado

 Para controlar la mayoría de las opciones de archivado, use el panel de control de Skype empresarial Server. Sin embargo, hay algunas opciones disponibles solo con el shell de administración de Skype empresarial Server. Estas opciones incluyen el archivado de mensajes duplicados y la exportación de datos archivados. Para obtener más información sobre el uso del panel de control de Skype empresarial Server y el shell de administración de Skype empresarial para administrar las directivas de archivado, consulte [administrar el archivado en Skype empresarial Server](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Obtener acceso a los datos archivados

El acceso a los datos archivados depende de dónde se almacenan los datos: 
  
- **Almacenamiento de Microsoft Exchange**. Si elige la opción de integración de Exchange, Skype empresarial Server deposita el contenido de archivado en el almacén de Exchange para todos los usuarios alojados en Exchange y los que han colocado sus buzones en conservación local. Los datos archivados se almacenan en la carpeta elementos recuperables de los buzones de usuario, que generalmente es invisible para los usuarios, y solo los usuarios con un rol de **Administración de detección** de Exchange pueden buscarlos. Exchange permite la búsqueda y detección federadas, junto con SharePoint, si se ha implementado. Para obtener más información sobre el almacenamiento, la retención y el descubrimiento de datos almacenados en Exchange, consulte la documentación de Exchange y SharePoint.
    
- **Almacenamiento de archivado de Skype empresarial Server**. Si configura las bases de datos de archivado de Skype empresarial Server, los depósitos de Skype empresarial Server archivan el contenido de las bases de datos de archivado de Skype empresarial Server para los usuarios que no estén alojados en Exchange y que no hayan puesto sus buzones en conservación local. This data is not searchable, but it can be exported to formats that are searchable using other tools. Para obtener más información sobre cómo exportar datos almacenados en bases de datos de archivado, consulte [exportar datos archivados en Skype empresarial Server](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Para más información

Para más información sobre el archivado, consulte los siguientes temas:
  
- [Implementar el archivado de Skype empresarial Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Administrar el archivado en Skype empresarial Server](../../manage/archiving/archiving.md)
    
Para obtener más información sobre cómo funciona conjuntamente Skype empresarial Server y Exchange, consulte [planear la integración de Skype empresarial y Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

