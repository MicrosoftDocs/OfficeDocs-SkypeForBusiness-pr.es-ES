---
title: Plan para el archivado en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Resumen: Lea este tema para obtener información sobre cómo planear el archivado en Skype para Business Server.'
ms.openlocfilehash: 164a3207153986e788a7db47b86014063e37e0e5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32236119"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Plan para el archivado en Skype para Business Server
 
**Resumen:** Lea este tema para obtener información sobre cómo planear el archivado en Skype para Business Server.
  
Las corporaciones y otras organizaciones están sujetas a una creciente cantidad de reglamentaciones gubernamentales y del sector que requieren la retención de determinados tipos de comunicaciones. Si su organización tiene estos requisitos, puede usar el archivado en Skype para Business Server para archivar mensajería instantánea (mi) y las comunicaciones de conferencia (reunión) para ayudar a admitir algunos de los requisitos de cumplimiento.
  
## <a name="archiving-components"></a>Componentes del archivado

Skype para Business Server utiliza los siguientes componentes de archivado:
  
- **Agentes de archivado**. Los agentes de archivado (también llamados agentes unificados de recolección de datos) se instalan y activan automáticamente en cada grupo de servidores front-end Enterprise Edition y en el servidor Standard Edition. Aunque los agentes de archivado se activan automáticamente, no se capturan realmente mensajes hasta que se habilite y configure correctamente el archivado. De manera predeterminada, el archivado se encuentra deshabilitado.
    
- **Almacenamiento de datos de archivado**. Almacenamiento de datos de Skype para Business Server se puede implementar como Skype para bases de datos de negocio de servidor SQL Server, o, si tiene una implementación de Exchange, integrada con el almacenamiento de Exchange. 
    
El archivado también requiere almacenamiento de archivos, pero el archivado usa el mismo almacenamiento de archivos que los servidores front-end o que el servidor Standard Edition.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Determinar los requisitos para el archivado de la organización

Para implementar el archivado, debe decidir cómo cumplir los requisitos de su organización para el archivado mediante la determinación de las siguientes:
  
- **Qué opción de almacenamiento usar**. Puede implementar el almacenamiento en una de las dos maneras o usar una combinación de ambas:
    
  - **Almacenamiento de Exchange.** Si tiene una implementación de Exchange, puede integrar Skype para Business Server y archivado de Exchange para que su Skype para Business Server y los datos de archivado de Exchange se almacenan juntos en Exchange. Si habilita la opción de integración de Microsoft Exchange, buzones de usuario habían alojado en el uso de Exchange Server almacenamiento de Exchange para los datos archivados, pero sólo si los buzones de correo se almacenaron en suspensión en contexto. De forma predeterminada, la integración de Microsoft Exchange no está habilitada.
    
  - **Skype para el almacenamiento de Business Server.** Si tiene usuarios que no están alojados en Exchange o que no tengan sus buzones poner en suspensión en contexto, o si no desea utilizar la integración de Microsoft Exchange para cualquier o todos los usuarios en su implementación, puede implementar Skype para bases de datos de archivado de servidor empresarial con S SQL Server.
    
- **Cuándo implementar el archivado**. Puede implementar el archivado como parte de su Skype inicial para la implementación de Business Server, o puede agregar a una implementación existente. Para utilizar Skype para el almacenamiento de archivado Business Server (bases de datos de SQL Server), use el generador de topología para agregar las bases de datos a la topología y, a continuación, vuelva a publicar la topología. Si todos los usuarios están ubicados en Exchange y disponer sus buzones en suspensión en contexto, no es necesario actualizar la topología, pero solo tiene que habilitar la integración de Microsoft Exchange almacenar los datos archivados en Exchange. 
    
- **Qué sitios y usuarios en la organización necesitan el archivado**. Puede configurar la configuración de archivado para toda la organización y, opcionalmente, para sitios específicos, grupos de servidores, los usuarios y grupos de usuarios.
    
- **Qué contenido se tiene que archivar**. Ya sea si especifica el archivado de forma global o para usuarios y sitios específicos, en cada uno de estos ámbitos, especifique si habilitará los siguientes tipos de contenido: 
    
  - Mensajes instantáneos de punto a punto
    
  - Conferencias (reuniones), que son mensajes instantáneos con varios participantes
    
  - Contenido de conferencias, como contenido que se carga (por ejemplo, documentos de la reunión) y contenido relacionado con el evento (por ejemplo, los usuarios que se unen o abandonan el evento, la carga de recursos compartidos y los cambios en la visibilidad)
    
  - Pizarras y sondeos compartidos durante una conferencia
    
- **Qué contenido no se puede archivar**. Los siguientes tipos de contenido no se pueden archivar: 
    
  - Transferencias de archivos de punto a punto
    
  - Audio o vídeo para conferencias y mensajes instantáneos de punto a punto
    
  - Escritorio y uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto
    
    Skype para Business Server también no archivar las conversaciones de Chat persistente. Para archivar las conversaciones de Chat persistente, debe habilitar y configurar el servicio de cumplimiento, que es un componente que se puede implementar con servidor de Chat persistente. Para obtener información detallada, consulte [Plan for Persistent Chat Server en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015. 
    
- **Cuánto tiempo es preciso conservar los materiales archivados**. La base de datos de archivado no está pensada para la retención a largo plazo y Skype para Business Server no proporciona una solución de exhibición de documentos electrónicos (búsqueda) para los datos archivados, por lo que necesitan datos va a mover a otro almacén. Skype para Business Server proporciona una herramienta de exportación de sesión que se puede utilizar para exportar los datos archivados y que crea que admite búsquedas transcripciones de los datos archivados. 
    
     Para la directiva global y para cada directiva de usuario y de sitio que cree, puede especificar cuándo se deben purgar datos archivados y exportados. Para obtener más información acerca de la depuración de datos, consulte [Administrar la purga de datos archivados de Skype para Business Server](../../manage/archiving/purging-of-archived-data.md). Para obtener más información acerca del uso de la sesión de exportación herramienta, consulte [Exportar datos archivados en Skype para Business Server](../../manage/archiving/export-archived-data.md).
    
- **Si archivar las comunicaciones internas o externas**. Puede habilitar el archivado de las comunicaciones internas (comunicaciones entre usuarios internos), las comunicaciones externas (comunicaciones que incluyen al menos un usuario fuera de la red interna), o ambas. Puede especificar estas opciones para toda la organización, o bien para grupos y sitios específicos. De forma predeterminada, no se habilita ninguna de estas opciones.
    
    > [!NOTE]
    > Controlar el archivado de comunicaciones internas o externas sólo está disponible para Skype para la directiva empresarial. Para el archivado Exchange integrado, comunicaciones internas y externas se archivan o no se archivan. 
  
- **Si implementar el modo crítico**. Si el archivado es un requisito para su organización, configurar el modo crítico se bloquean las sesiones de mensajería instantánea y conferencias en el caso de un Skype para errores del servidor de negocio que podrían impedir el archivado. Por ejemplo: 
    
  - Un problema con la Skype para el servicio de almacenamiento de Business Server. En este caso, la mensajería instantánea (MI) se bloquea para los usuarios que están habilitados para el archivado.
    
  - Un recurso compartido de archivo no disponible o un problema con el servicio de almacenamiento. En este caso, todas las conferencias activas alojadas en el grupo de servidores en el momento del error se cambian al modo restringido y no se puede activar conferencias nuevas.
    
    Tanto la mensajería instantánea como las conferencias se recuperan automáticamente después de que se corrigen los errores.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Seleccionar las opciones de configuración y la implementación del archivado

El archivado se instala automáticamente en cada servidor front-end al implementar el servidor, pero el archivado no está habilitado hasta que se configura. La manera de configurarlo depende de la forma de implementar el archivado. Puede implementar el archivado de una de las siguientes maneras:
  
- Usar el almacenamiento de información de Microsoft Exchange
    
- Usar Skype para el almacenamiento de Business Server
    
> [!NOTE]
> Si se implementa ambos Skype para bases de datos de archivado de servidor empresarial y habilitar la integración de Microsoft Exchange, las directivas de Exchange invalidar Skype para Business Server directivas de archivado, pero sólo para los usuarios que están ubicados en Exchange y que han tenido sus buzones poner en Retención en contexto. Skype para el archivado de negocio depende de la directiva de retención en contexto de Microsoft Exchange. 
  
Si implementa el archivado para un servidor Standard Edition o grupo de servidores Front-End, se debe habilitar para todos los otros grupos de servidores Front-End y servidores Standard Edition en la implementación. Si el archivado no está habilitado en el grupo de servidores en el que se hospeda una conversación o una reunión, puede que no se puedan archivar todos los datos de la conferencia. El archivado seguirá funcionando para todos los mensajes de la mensajería instantánea (MI), pero posiblemente no se archiven los eventos y el contenido de las conferencias.
  
> [!NOTE]
> Para habilitar la delegación de tareas administrativas que se mantiene los estándares de seguridad de su organización, Skype para Business Server usa el control de acceso basado en roles (RBAC). Con RBAC, se concede el privilegio administrativo al asignar a los usuarios roles administrativos predefinidos. Para configurar Skype para configuraciones y directivas de archivado de negocio, el usuario debe estar asignado a la función CsArchivingAdministrator (a menos que la configuración se realiza directamente en el servidor donde el archivado se implementa, en lugar de forma remota desde otro equipo ). Para obtener una lista de los derechos de usuario, permisos y las funciones necesarias para el archivado de implementación, vea [implementar el archivado de Skype para Business Server](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Si utiliza la integración de Microsoft Exchange, configuración de directivas de Exchange requiere permisos y derechos de administrador adecuados. Para obtener información detallada, consulte la documentación de Exchange. 
  
### <a name="microsoft-exchange-storage"></a>Almacenamiento de información de Microsoft Exchange

 Si elige la integración de Microsoft Exchange, use las directivas de Exchange y las configuraciones para controlar el archivado de Skype para Business Server. Puede configurar la opción de integración de Microsoft Exchange en el nivel global, el nivel de sitio y el nivel de grupo de servidores. Si la implementación incluye varios bosques, debe sincronizar la configuración entre Skype para Business Server y Exchange. Tendrá que determinar lo siguiente:
  
- Si archivar la mensajería instantánea (MI), las conferencias o ambas
    
- Si se debe implementar el modo crítico, lo que bloquea las sesiones de mensajería instantánea y conferencias en caso de un Skype para error de Business Server 
    
- Selección de la opción de integración de Microsoft Exchange para usar Exchange para el almacenamiento de datos archivados
    
Para obtener información acerca de cómo configurar las directivas de retención de Exchange local y la configuración que admita el archivado, vea la documentación del producto de Exchange.
  
### <a name="skype-for-business-server-storage"></a>Almacenamiento de Skype Empresarial Server

Si elige Skype para el almacenamiento de Business Server, use Skype para las directivas de archivado Business Server y las configuraciones para controlar el archivado está habilitado e implementado. Skype para el almacenamiento de Business Server usa bases de datos de SQL Server, por lo que tendrá que agregar las bases de datos de SQL Server correspondientes a la topología, a continuación, configure las directivas de archivado. 
  
### <a name="add-storage-databases-to-your-topology"></a>Agregar bases de datos de almacenamiento a la topología

Al agregar las bases de datos de almacenamiento de SQL Server a la topología, puede elegir para combinar las bases de datos de archivado con cualquiera de las siguientes opciones:
  
- Base de datos de supervisión
    
- Base de datos back-end de un grupo de servidores front-end Enterprise Edition
    
> [!NOTE]
> El servidor que hospeda la base de datos de archivado puede hospedar otras bases de datos. Pero, si piensa combinar la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede crecer mucho. Por este motivo, no recomendamos la combinación de la base de datos de archivado con la base de datos back-end. 
  
Si instala la base de datos de archivado con la base de datos de supervisión, base de datos back-end o ambas de estas bases de datos, se puede utilizar una sola instancia SQL para cualquiera o todas las bases de datos, o puede utilizar una instancia SQL diferente para cada base de datos, con lo siguiente limitación: instancia SQL Each puede contener una sola base de datos back-end, única base de datos de supervisión y única base de datos de archivado.
  
Para obtener información detallada sobre la combinación de todos los roles de servidor y las bases de datos, vea [Conceptos básicos de la topología de Skype para Business Server](../../plan-your-deployment/topology-basics/topology-basics.md). Para obtener información detallada acerca de cómo actualizar la topología para incluir bases de datos de almacenamiento de información, vea [crear y publicar la nueva topología de Skype para Business Server](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Determinar las opciones de archivado y las directivas de usuario

Es preciso que determine lo siguiente:
  
- Si habilitar (o deshabilitar) el archivado para las comunicaciones internas y externas
    
- Si archivar la mensajería instantánea (MI), las conferencias o ambas
    
- Si se debe implementar el modo crítico, lo que bloquea las sesiones de mensajería instantánea y conferencias en caso de un Skype para error de Business Server 
    
- Si habilitar las directivas para usuarios y grupos específicos
    
Skype para las opciones de archivado de servidor empresarial puede especificarse en los siguientes niveles. 
  
- **Opción de ámbito global**. Esta es la configuración de archivado predeterminada y se aplica a toda la implementación. Se crea cuando implementa Skype para Business Server y, de forma predeterminada, deshabilita el archivado de comunicaciones internas y externas. Esta opción no se puede eliminar. Si elige la opción de eliminarla, la opción global se restablece a la configuración predeterminada.
    
- **Opciones en el ámbito de sitio**. Puede habilitar o deshabilitar el archivado para uno o más sitios específicos al crear y configurar una opción de archivado para el sitio. Todas las opciones de archivado para el sitio que cree se pueden eliminar. Una opción de archivado para el sitio reemplaza la opción global, pero solo para el sitio especificado en la opción. 
    
    Por ejemplo, si habilita el archivado para las comunicaciones internas y externas en la configuración global y crea una configuración de sitio en la que deshabilita el archivado para las comunicaciones externas, solo se archivarán las comunicaciones internas para ese sitio. Otro ejemplo sería el siguiente: si habilita el archivado solo para la mensajería instantánea (MI) en la configuración global y crea una configuración de sitio en la que habilita el archivado tanto para la mensajería instantánea (MI) como para las conferencias, solo se archivarán las conferencias para el sitio, y no para el resto de la organización.
    
- **Opciones en el ámbito de grupo**. Puede especificar la configuración de archivado para uno o más grupos específicos al crear y establecer una configuración para el grupo individual. Una configuración de archivado para un grupo solo existe si se la crea. Puede modificar y eliminar cualquier configuración de archivado para el grupo. Una configuración de archivado de grupo reemplaza la configuración global y cualquier configuración de archivado que haya creado. 
    
    Por ejemplo, supongamos que habilita el archivado de mensajería instantánea sólo en la configuración global, a continuación, crear una configuración de nivel de sitio en el que se habilita el archivado de mensajería instantánea y conferencias y, a continuación, crear una configuración de nivel de grupo de servidores en el que se habilita el archivado sólo para mensajería instantánea . ¿Se archivan las comunicaciones para mensajería instantánea y conferencias para todos los usuarios del sitio excepto los usuarios alojados en el grupo de servidores especificado en la configuración en el nivel de grupo de servidores. Todos los demás usuarios de la organización, debería habilitar el archivado sólo para mensajería instantánea.
    
- **Directivas de archivado de usuario**. Puede habilitar o deshabilitar el archivado para uno o más usuarios y grupos específicos al crear, configurar y aplicar una directiva de archivado de usuario para usuarios y grupos de usuarios específicos. Puede eliminar cualquier directiva de archivado de usuario que cree y puede cambiar a qué usuarios y a qué grupo de usuarios se aplica la directiva. Una directiva de archivado de usuario reemplaza la directiva global y todas las directivas de sitio, pero solo para los usuarios y los grupos de usuarios a quienes se aplique la política. 
    
    Por ejemplo, suponga que deshabilita el archivado de comunicaciones internas y externas en la configuración global, crear una directiva de nivel de sitio en el que se habilita el archivado de comunicaciones internas y externas y, a continuación, crear una directiva de nivel de usuario en el que se deshabilitar el archivado para comunicaciones externas. ¿Se archivan las comunicaciones para las comunicaciones externas e internas de todos los usuarios del sitio excepto para los usuarios a quienes se aplican la directiva de nivel de usuario--para estos usuarios ¿se archivan las comunicaciones sólo internas.
    
Para obtener información detallada acerca de cómo configurar las configuraciones de archivado iniciales al implementar el archivado, vea [implementar el archivado de Skype para Business Server](../../deploy/deploy-archiving/deploy-archiving.md). Para obtener información detallada acerca de cómo administrar el archivado después de la implementación, vea [administrar el archivado en Skype para Business Server](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Herramientas de configuración del archivado

 Controlar la mayoría de las opciones de archivado mediante el uso de la Skype para el Panel de Control de servidor empresarial. Sin embargo, hay algunas opciones disponibles sólo mediante la Skype para Shell de administración de servidor empresarial. Estas opciones incluyen archivar mensajes duplicados y exportar los datos archivados. Para obtener más información acerca del uso de la Skype para el Panel de Control de servidor empresarial y la Skype para Shell de administración de servidor empresarial para administrar las directivas de archivado, vea [administrar el archivado en Skype para Business Server](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Obtener acceso a los datos archivados

El acceso a los datos archivados depende de dónde se almacenan los datos: 
  
- **Almacenamiento de información de Microsoft Exchange**. Si elige la opción de integración de Exchange, Skype para Business Server depósitos el contenido archivado en el almacén de Exchange para todos los usuarios que están alojados en Exchange, y que ha mantenido sus buzones poner en suspensión en contexto. Los datos archivados se almacenan en la carpeta de elementos recuperables de los buzones de usuario, que es generalmente invisible para los usuarios y sólo se puede buscar los usuarios con una función de **Administración de detección** de Exchange. Exchange habilita búsqueda federada y detección, junto con SharePoint, si se ha implementado. Para obtener más información acerca del almacenamiento, retención y detección de datos almacenados en Exchange, consulte la documentación de Exchange y SharePoint.
    
- **Skype para el almacenamiento de archivado Business Server**. Si configurar Skype para bases de datos de archivado de servidor empresarial, Skype para los depósitos de Business Server no archivado del contenido en el Skype para bases de datos de archivado de servidor empresarial de los usuarios alojados en Exchange y que no tengan sus buzones poner en suspensión en contexto. This data is not searchable, but it can be exported to formats that are searchable using other tools. Para obtener información detallada acerca de cómo exportar datos almacenados en bases de datos de archivado, vea [Exportar datos archivados en Skype para Business Server](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Para más información

Para más información sobre el archivado, consulte los siguientes temas:
  
- [Implementar el archivado de Skype para Business Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Administrar el archivado en Skype para Business Server](../../manage/archiving/archiving.md)
    
Para obtener más información acerca de cómo Skype para Business Server y Exchange funcionan conjuntamente, vea [Planear la integración de Skype para empresas y Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

