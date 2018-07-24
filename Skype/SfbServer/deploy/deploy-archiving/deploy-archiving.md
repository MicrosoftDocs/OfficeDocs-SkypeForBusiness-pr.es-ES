---
title: Implementar el archivado de Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Resumen: Lea este tema para aprender a implementar el archivado de Skype para Business Server.'
ms.openlocfilehash: b1df3b3b14ec31f0c2c4d3d94f41ff23411c7f45
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997634"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Implementar el archivado de Skype para Business Server
 
**Resumen:** Lea este tema para aprender a implementar el archivado de Skype para Business Server.
  
El archivado se instala automáticamente en cada servidor Front-End en su Skype para la implementación de Business Server, pero necesitará realizar inicial del programa de instalación y los pasos de configuración antes de que se puede usar. Antes de empezar, asegúrese de que está familiarizado con los conceptos de [planeación para el archivado en Skype para Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="deployment-checklist"></a>Lista de comprobación de la implementación

La configuración de archivado depende de la opción de almacenamiento que elija: 
  
- Si utiliza la integración de Microsoft Exchange para todos los usuarios de la implementación, no es necesario configurar Skype para las directivas de archivado para los usuarios de Business Server. En su lugar, configure las directivas de retención de Exchange local para admitir el archivado para los usuarios alojados en Exchange, con sus buzones poner en suspensión en contexto. Para obtener información detallada acerca de cómo configurar estas directivas, consulte la documentación de producto de Exchange.
    
- Si no utiliza la integración de Microsoft Exchange para todos los usuarios de la implementación, necesite para agregar Skype para Business Server archivar bases de datos (bases de datos de SQL Server) a la topología, publicar la topología actualizada y a continuación, configure las directivas de archivado y configuración de los usuarios. Puede implementar bases de datos de archivado a la vez que implementa la topología inicial o después de implementar, como mínimo, un grupo de servidores front-end o un servidor Standard Edition. En este documento se describe cómo implementar bases de datos de archivado agregándolas a una implementación existente.
    
Si habilita el archivado en un grupo de servidores front-end o en un servidor Standard Edition, será necesario que lo habilite para todos los demás grupos de servidores de front-end y los servidores Standard Edition de su implementación, ya que los usuarios cuyas comunicaciones se tienen que archivar pueden ser invitados a una conversación de mensajería instantánea (MI) en grupo o a reuniones hospedadas en un grupo de servidores diferente. Si el archivado no está habilitado en el grupo de servidores donde se hospeda la conversación o la reunión, puede que no se almacene toda la sesión. En estos casos, se podrán seguir archivando los mensajes instantáneos de los usuarios que tengan habilitado el archivado, pero no los archivos de contenido de conferencias ni los eventos creados al unirse a conferencias o abandonarlas.
  
> [!IMPORTANT]
> Si el archivado es esencial en la organización por motivos de cumplimiento, asegúrese de implementar el archivado, configurar directivas y otras opciones en el nivel apropiado y, a continuación, activar el archivado para todos los usuarios adecuados, antes de permitir que esos usuarios de Skype para Business Server. 
  
La tabla siguiente proporciona información general de los pasos necesarios para implementar el archivado en una topología existente.
  
|**Fase**|**Pasos**|**Roles y pertenencias a grupos**|**Documentación**|
|:-----|:-----|:-----|:-----|
|**Instalar los requisitos previos de hardware y software** <br/> |Para utilizar la integración de Microsoft Exchange (con Exchange para el almacenamiento de archivado para algunos o todos los usuarios), necesita una implementación existente de Exchange.  <br/> Para usar bases de datos independientes (con bases de datos de SQL Server) para el almacén de archivado para algunos o todos los usuarios, necesitará SQL Server en el servidor que almacenará los datos de archivado.  <br/> El archivado se ejecuta en servidores front-end de un grupo de servidores Enterprise y en servidores Standard Edition. No hay ningún requisito adicional de hardware o de software aparte de los necesarios para instalar dichos servidores.  <br/> |Usuario de dominio que es miembro del grupo de administradores locales.  <br/> |[Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisitos del entorno para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Plan para la integración de Skype Empresarial y Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Requisitos del sistema para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Crear la topología interna adecuada para admitir el archivado (sólo si no usando la integración de Microsoft Exchange para todos los usuarios de la implementación)** <br/> |Ejecute Topology Builder para agregar Skype para Business Server archivar bases de datos (bases de datos de SQL Server) a la topología y, a continuación, publicar la topología.  <br/> |A fin de definir una topología para incorporar bases de datos de archivado, se necesita una cuenta que pertenezca al grupo de usuarios locales.  <br/> Para publicar la topología, una cuenta que sea miembro del grupo Administradores de dominio y grupo RTCUniversalServerAdmins y que tiene permisos de control total (lectura/escritura/modificar) en el recurso compartido de archivos que se usará para la Skype para almacén de archivos de Business Server (para que topología El generador puede configurar las DACL necesarias).  <br/> |[Agregar bases de datos de archivado a una implementación existente de Skype para Business Server](add-archiving-databases.md) <br/> |
|**Configurar la autenticación de servidor a servidor (sólo si se usa la integración de Microsoft Exchange)** <br/> |Configuración de servidores para habilitar la autenticación entre Skype para Business Server y Exchange. Se recomienda ejecutar **Test-CsExchangeStorageConnectivity testuser_sipUri-volcado de archivos de carpeta** para validar la conectividad de almacenamiento de archivado antes de habilitar el archivado de Exchange. <br/> |Una cuenta con los permisos necesarios para administrar certificados en los servidores.  <br/> |Administrar la autenticación de servidor a servidor  <br/> |
|**Configurar las opciones de archivado y las directivas** <br/> |Configuración de archivado, incluyendo si se va a usar la integración de Microsoft Exchange, la directiva global y las directivas de usuario y de sitio (cuando no usando la integración de Microsoft Exchange para todo el almacenamiento de datos) y el archivado específico opciones, como el modo crítico y datos exportación y depuración.  <br/> Si utiliza la integración de Microsoft Exchange, configure las directivas de retención en contexto de Exchange según corresponda.  <br/> |Grupo RTCUniversalServerAdmins (solo Windows PowerShell) o asigne los usuarios al rol CSArchivingAdministrator o CSAdministrator.  <br/> |[Configurar las opciones de archivado para Skype para Business Server](configure-archiving-options.md) <br/> Documentación del producto de Exchange (si está usando la integración de Microsoft Exchange).  <br/> |
   

