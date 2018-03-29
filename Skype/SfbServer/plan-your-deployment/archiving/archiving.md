---
title: Planificar el archivado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Resumen: Leer este tema para aprender a planear para archiving en Skype para Business Server 2015.'
ms.openlocfilehash: 53895a404c2502a0d54553fda979add6031b09f6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-archiving-in-skype-for-business-server-2015"></a>Planificar el archivado en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a planear para archiving en Skype para Business Server 2015.
  
Las corporaciones y otras organizaciones están sujetas a una creciente cantidad de reglamentaciones gubernamentales y del sector que requieren la retención de determinados tipos de comunicaciones. Si su organización tiene dichos requisitos, puede utilizar archiving en Skype para Business Server 2015 para archiving de mensajería instantánea (IM) y comunicaciones de la conferencia (reunión) para ayudar a mantener algunos de los requerimientos de cumplimiento de normas.
  
## <a name="archiving-components"></a>Componentes del archivado

Skype para Business Server utiliza los siguientes componentes de archiving:
  
- **Agentes de archivado**. Los agentes de archivado (también llamados agentes unificados de recolección de datos) se instalan y activan automáticamente en cada grupo de servidores front-end Enterprise Edition y en el servidor Standard Edition. Aunque los agentes de archivado se activan automáticamente, no se capturan realmente mensajes hasta que se habilite y configure correctamente el archivado. De manera predeterminada, el archivado se encuentra deshabilitado.
    
- **Almacenamiento de datos de archivado**. Almacenamiento de datos para Skype para Business Server 2015 puede se implementa como Skype para bases de datos de SQL Server del servidor de empresa, o, si tiene una implementación de Exchange, integrada con almacenamiento de información de Exchange. 
    
El archivado también requiere almacenamiento de archivos, pero el archivado usa el mismo almacenamiento de archivos que los servidores front-end o que el servidor Standard Edition.
  
Para obtener una lista de requisitos de hardware y software para archiving, vea [requisitos de Hardware y software para archiving en Skype para Business Server 2015](hardware-and-software-requirements.md).
  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Determinar los requisitos para el archivado de la organización

Para implementar el archiving, es necesario decidir cómo cumplir los requisitos de su organización para archiving mediante la determinación de lo siguiente:
  
- **Qué opción de almacenamiento usar**. Puede implementar el almacenamiento en una de las dos maneras o usar una combinación de ambas:
    
  - **Almacenamiento de información de Exchange.** Si tiene una implementación de Exchange, puede integrar Skype para Business Server y Exchange archiving para que su Skype para Business Server y los datos de Exchange archivado se almacenan juntas en Exchange. Si habilita la opción de integración de Microsoft Exchange, buzones de usuarios alojados en el uso de Exchange Server almacenamiento de información de Exchange para los datos archivados, pero sólo si los buzones han sido puestos en mantenga In situ. De forma predeterminada, no está habilitada la integración de Microsoft Exchange.
    
  - **Skype para el almacenamiento de Business Server.** Si tiene usuarios que no estén alojados en Exchange o que no tengan sus buzones poner en posesión en el lugar, o si no desea utilizar la integración de Microsoft Exchange para cualquiera o todos los usuarios en la implementación, puede implementar Skype para bases de datos de archivado de Business Server usando S QL Server.
    
- **Cuándo implementar el archivado**. Puede implementar archiving como parte de su Skype inicial para la implementación de Business Server, o puede agregarlo a una implementación existente. Para utilizar Skype para el almacenamiento de archiving Business Server (bases de datos de SQL Server), utilice el generador de topología para agregar las bases de datos a la topología y, a continuación, vuelva a publicar la topología. Si todos los usuarios alojados en Exchange y han puesto a sus buzones en mantenga In situ, no tiene que actualizar la topología, pero sólo necesita habilitar la integración de Microsoft Exchange almacenar los datos archivados en Exchange. 
    
- **Qué sitios y usuarios en la organización necesitan el archivado**. Puede configurar valores de archivado para toda la organización y, opcionalmente, para sitios específicos, grupos, usuarios y grupos de usuarios.
    
- **Qué contenido se tiene que archivar**. Ya sea si especifica el archivado de forma global o para usuarios y sitios específicos, en cada uno de estos ámbitos, especifique si habilitará los siguientes tipos de contenido: 
    
  - Mensajes instantáneos de punto a punto
    
  - Conferencias (reuniones), que son mensajes instantáneos con varios participantes
    
  - Contenido de conferencias, como contenido que se carga (por ejemplo, documentos de la reunión) y contenido relacionado con el evento (por ejemplo, los usuarios que se unen o abandonan el evento, la carga de recursos compartidos y los cambios en la visibilidad)
    
  - Pizarras y sondeos compartidos durante una conferencia
    
- **Qué contenido no se puede archivar**. Los siguientes tipos de contenido no se pueden archivar: 
    
  - Transferencias de archivos de punto a punto
    
  - Audio o vídeo para conferencias y mensajes instantáneos de punto a punto
    
  - Escritorio y uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto
    
    También Skype para Business Server no archiva conversaciones de Chat persistentes. Para archivar las conversaciones de Chat persistentes, debe habilitar y configurar el servicio de cumplimiento de normas, que es un componente que puede implementarse con el servidor de charla persistente. Para obtener más información, vea [Planear persistente Server Chat de Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).
    
- **Cuánto tiempo es preciso conservar los materiales archivados**. La base de datos de archivado no está pensado para la retención a largo plazo y Skype para Business Server no proporciona una solución de e-discovery (Buscar) para los datos archivados, por lo que deben moverse a otro almacenamiento datos. Skype para Business Server proporciona una herramienta de exportación de sesión que puede utilizar para exportar los datos archivados y que crea las transcripciones de búsquedas de los datos archivados. 
    
     Para la directiva global y para cada directiva de sitio y el usuario que cree, puede especificar cuándo se deben purgar los datos archivados y exportados. Para obtener más información acerca de la depuración de datos, consulte [Administrar la purga de los datos archivados en Skype para Business Server 2015](../../manage/archiving/purging-of-archived-data.md). Para obtener más información acerca de cómo utilizar la sesión de la herramienta de exportación, vea [Exportar datos archivados en Skype para Business Server 2015](../../manage/archiving/export-archived-data.md).
    
- **Si archivar las comunicaciones internas o externas**. Puede habilitar el archivado de las comunicaciones internas (comunicaciones entre usuarios internos), las comunicaciones externas (comunicaciones que incluyen al menos un usuario fuera de la red interna), o ambas. Puede especificar estas opciones para toda la organización, o bien para grupos y sitios específicos. De forma predeterminada, no se habilita ninguna de estas opciones.
    
    > [!NOTE]
    > Controlar el archivado de comunicaciones internas o externas sólo está disponible para Skype para las políticas del negocio. Para archiving de Exchange integrado, comunicaciones internas y externas se archivan o no archivar. 
  
- **Si implementar el modo crítico**. El archiving es un requisito para su organización, configuración de modo crítico se bloquearán las sesiones de mensajería instantánea y conferencias en caso de un Skype error Business Server que impedirían que el archiving. Por ejemplo: 
    
  - Un problema con el Skype para el servicio de almacenamiento de información de Business Server. En este caso, la mensajería instantánea (MI) se bloquea para los usuarios que están habilitados para el archivado.
    
  - Un recurso compartido de archivo no disponible o un problema con el servicio de almacenamiento. En este caso, todas las conferencias activas alojadas en el grupo de servidores en el momento del error se cambian al modo restringido y no se puede activar conferencias nuevas.
    
    Tanto la mensajería instantánea como las conferencias se recuperan automáticamente después de que se corrigen los errores.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Seleccionar las opciones de configuración y la implementación del archivado

El archivado se instala automáticamente en cada servidor front-end al implementar el servidor, pero el archivado no está habilitado hasta que se configura. La manera de configurarlo depende de la forma de implementar el archivado. Puede implementar el archivado de una de las siguientes maneras:
  
- Utilizar almacenamiento de información de Microsoft Exchange
    
- Usar Skype para el almacenamiento de Business Server
    
> [!NOTE]
> Si se implementa ambos Skype para bases de datos de archivado de Business Server y habilitar la integración de Microsoft Exchange, directivas de Exchange reemplazar Skype para políticas de archiving de Business Server, pero sólo para los usuarios que están alojados en Exchange y que han tenido sus buzones poner en En lugar suspensión. Skype para archiving empresarial depende de la directiva de Microsoft Exchange en el mismo lugar mantenga. 
  
Si se implementa archivado para un servidor Standard Edition o grupo de servidores Front-End, se debe habilitar para todos los demás grupos de Front-End y los servidores Standard Edition en la implementación. Si el archivado no está habilitado en el grupo de servidores en el que se hospeda una conversación o una reunión, puede que no se puedan archivar todos los datos de la conferencia. El archivado seguirá funcionando para todos los mensajes de la mensajería instantánea (MI), pero posiblemente no se archiven los eventos y el contenido de las conferencias.
  
> [!NOTE]
> Para habilitar la delegación de tareas administrativas al tiempo que mantiene los estándares de seguridad de su organización, Skype para Business Server utiliza control de acceso basado en roles (RBAC). Con RBAC, se concede el privilegio administrativo al asignar a los usuarios roles administrativos predefinidos. Para configurar Skype para configuraciones y políticas de archiving empresarial, se debe asignar el usuario a la función CsArchivingAdministrator (a menos que la configuración se realiza directamente en el servidor donde archivado está implementado, en lugar de remotamente desde otro equipo ). Para obtener una lista de los derechos de usuario, permisos y funciones necesarias para archiving de implementación, vea [implementar archiving de Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Si utiliza la integración de Microsoft Exchange, configuración de directivas de Exchange requiere permisos y derechos de administrador adecuados. Para obtener más información, consulte la documentación de Exchange. 
  
### <a name="microsoft-exchange-storage"></a>Almacenamiento de información de Microsoft Exchange

 Si decide que la integración de Microsoft Exchange, utilice las directivas de Exchange y configuraciones para controlar el archiving de Skype para Business Server. Puede configurar la opción de integración de Microsoft Exchange en el nivel global, el nivel de sitio y el nivel de grupo. Si su implementación incluye varios bosques, debe sincronizar la configuración entre Skype para Business Server y Exchange. Tendrá que determinar lo siguiente:
  
- Si archivar la mensajería instantánea (MI), las conferencias o ambas
    
- Si implementa el modo crítico, que bloquea las sesiones de mensajería instantánea y conferencias en el caso de un Skype para error Business Server 
    
- Selección de la opción de integración de Microsoft Exchange para utilizar Exchange para el almacenamiento de los datos archivados
    
Para obtener información acerca de cómo configurar directivas de Exchange en el mismo lugar mantenga y configuración para soportar archiving, consulte la documentación del producto Exchange.
  
### <a name="skype-for-business-server-storage"></a>Almacenamiento de Skype Empresarial Server

Si elige Skype para el almacenamiento de Business Server, utilizar Skype para configuraciones y políticas de archiving Business Server para controlar el archivado está habilitado e implementado. Skype para el almacenamiento de Business Server utiliza bases de datos de SQL Server, por lo que tendrá que agregar las bases de datos de SQL Server a la topología, a continuación, configurar sus políticas de archiving. 
  
### <a name="add-storage-databases-to-your-topology"></a>Agregar bases de datos de almacenamiento a la topología

Al agregar bases de datos de almacenamiento de SQL Server a la topología, puede colocar las bases de datos de archivado con cualquiera de las siguientes acciones:
  
- Base de datos de supervisión
    
- Base de datos back-end de un grupo de servidores front-end Enterprise Edition
    
> [!NOTE]
> El servidor que hospeda la base de datos de archivado puede hospedar otras bases de datos. Pero, si piensa combinar la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede crecer mucho. Por este motivo, no recomendamos la combinación de la base de datos de archivado con la base de datos back-end. 
  
Si coloca la base de datos de archivado con la base de datos de supervisión, base de datos back-end o ambas bases de datos, puede utilizar una única instancia SQL para cualquiera o todas las bases de datos o puede utilizar una instancia independiente de SQL para cada base de datos, con el siguiente limitación: instancia de cada SQL puede contener una sola base de datos back-end, única base de datos de supervisión y única base de datos de archivado.
  
Para obtener más información acerca de la colocación de todos los roles de servidor y las bases de datos, consulte [Aspectos básicos de la topología para Skype para Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md). Para obtener más información acerca de cómo actualizar la topología para incluir bases de datos de almacenamiento de información, consulte [crear y publicar la nueva topología en Skype para Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Determinar las opciones de archivado y las directivas de usuario

Es preciso que determine lo siguiente:
  
- Si habilitar (o deshabilitar) el archivado para las comunicaciones internas y externas
    
- Si archivar la mensajería instantánea (MI), las conferencias o ambas
    
- Si implementa el modo crítico, que bloquea las sesiones de mensajería instantánea y conferencias en el caso de un Skype para error Business Server 
    
- Si habilitar las directivas para usuarios y grupos específicos
    
Skype para las opciones de archivado de Business Server puede especificarse en los siguientes niveles. 
  
- **Opción de ámbito global**. Esta es la configuración de archivado predeterminada y se aplica a toda la implementación. Se crea al implementar Skype para Business Server y, de forma predeterminada, deshabilita el archivado de comunicaciones internas y externas. Esta opción no se puede eliminar. Si elige la opción de eliminarla, la opción global se restablece a la configuración predeterminada.
    
- **Opciones en el ámbito de sitio**. Puede habilitar o deshabilitar el archivado para uno o más sitios específicos al crear y configurar una opción de archivado para el sitio. Todas las opciones de archivado para el sitio que cree se pueden eliminar. Una opción de archivado para el sitio reemplaza la opción global, pero solo para el sitio especificado en la opción. 
    
    Por ejemplo, si habilita el archivado para las comunicaciones internas y externas en la configuración global y crea una configuración de sitio en la que deshabilita el archivado para las comunicaciones externas, solo se archivarán las comunicaciones internas para ese sitio. Otro ejemplo sería el siguiente: si habilita el archivado solo para la mensajería instantánea (MI) en la configuración global y crea una configuración de sitio en la que habilita el archivado tanto para la mensajería instantánea (MI) como para las conferencias, solo se archivarán las conferencias para el sitio, y no para el resto de la organización.
    
- **Opciones en el ámbito de grupo**. Puede especificar la configuración de archivado para uno o más grupos específicos al crear y establecer una configuración para el grupo individual. Una configuración de archivado para un grupo solo existe si se la crea. Puede modificar y eliminar cualquier configuración de archivado para el grupo. Una configuración de archivado de grupo reemplaza la configuración global y cualquier configuración de archivado que haya creado. 
    
    Por ejemplo, habilitar el archivado de mensajería instantánea sólo en la configuración global, se supone, a continuación, crear una configuración de nivel de sitio en el que habilitar el archivado de mensajería instantánea y conferencias y, a continuación, crear una configuración de nivel de grupo en el que habilitar el archivado sólo para mensajería instantánea . Se archivan las comunicaciones de mensajería instantánea y conferencias para todos los usuarios del sitio excepto los usuarios alojados en el grupo especificado en la configuración de nivel de grupo. Para los demás usuarios de la organización, debería habilitar el archivado sólo para mensajería instantánea.
    
- **Directivas de archivado de usuario**. Puede habilitar o deshabilitar el archivado para uno o más usuarios y grupos específicos al crear, configurar y aplicar una directiva de archivado de usuario para usuarios y grupos de usuarios específicos. Puede eliminar cualquier directiva de archivado de usuario que cree y puede cambiar a qué usuarios y a qué grupo de usuarios se aplica la directiva. Una directiva de archivado de usuario reemplaza la directiva global y todas las directivas de sitio, pero solo para los usuarios y los grupos de usuarios a quienes se aplique la política. 
    
    Por ejemplo, supongamos que deshabilita el archivado de comunicaciones internas y externas en la configuración global, crear una directiva de nivel de sitio en el que habilitar el archivado de comunicaciones internas y externas y, a continuación, crear una directiva de nivel de usuario en el que se deshabilitar el archivado para comunicaciones externas. ¿Se archivan las comunicaciones para las comunicaciones internas y externas para todos los usuarios del sitio excepto los usuarios a las que aplicar la directiva de nivel de usuario--para estos usuarios podrían archivarse las comunicaciones internas sólo.
    
Para obtener más información acerca de cómo establecer configuraciones de archivado iniciales al implementar archiving, vea [implementar archiving de Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md). Para obtener más información acerca de cómo administrar el archivado después de la implementación, vea [administrar el archivado en Skype para Business Server 2015](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Herramientas de configuración del archivado

 Controlar la mayoría de opciones de archivado utilizando el Skype para el Panel de Control de servidor empresarial. Sin embargo, hay algunas opciones disponibles sólo mediante el Skype para el Shell de administración de servidor empresarial. Estas opciones incluyen archivar mensajes duplicados y exportar los datos archivados. Para obtener más información acerca de cómo utilizar el Skype para Panel de Control de servidor empresarial y el Skype para el Shell de administración de servidor de negocios para administrar políticas de archiving, vea [administrar el archivado en Skype para Business Server 2015](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Obtener acceso a los datos archivados

El acceso a los datos archivados depende de dónde se almacenan los datos: 
  
- **Almacenamiento de información de Microsoft Exchange**. Si elige la opción de integración de Exchange, Skype para Business Server depósitos el contenido archivado en el almacén de Exchange para todos los usuarios que están alojados en Exchange, y que han tenido sus buzones poner en posesión en el lugar. Los datos archivados se almacenan en la carpeta de elementos recuperables de los buzones de usuario, que es generalmente invisible para los usuarios y sólo se puede buscar por usuarios con una función de **Descubrimiento de administración** de Exchange. Exchange habilita búsqueda federada y descubrimiento, junto con SharePoint, si se ha implementado. Para obtener más detalles acerca del almacenamiento, retención y descubrimiento de datos almacenados en Exchange, consulte la documentación de Exchange y SharePoint.
    
- **Skype para el almacenamiento de archiving Business Server**. Si configura Skype para Business Server Archiving de bases de datos, Skype para los depósitos de Business Server archiving de contenido en el Skype para Business Server Archiving de bases de datos para los usuarios no estén alojados en Exchange y que no tengan sus buzones poner en posesión en el lugar. Estos datos no son búsquedos, pero se puede exportar a los formatos que se pueden buscar mediante otras herramientas. Para obtener más información acerca de cómo exportar datos almacenados en bases de datos de archivado, vea [Exportar datos archivados en Skype para Business Server 2015](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Para más información

Para más información sobre el archivado, consulte los siguientes temas:
  
- [Implementar archiving de Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Administrar el archivado en Skype para Business Server 2015](../../manage/archiving/archiving.md)
    
Para obtener más información acerca de cómo Skype para Business Server y Exchange trabajan juntos, vea [Planear la integración de Skype para empresas y Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

