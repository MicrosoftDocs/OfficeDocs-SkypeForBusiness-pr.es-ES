---
title: Implementar el archivado para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Resumen: lea este tema para obtener información sobre cómo implementar el archivado para Skype Empresarial Server.'
ms.openlocfilehash: 1bc478794c591e99d8372165491563c6c0b909caf94902741b03b21aef48c8cb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54287659"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Implementar el archivado para Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo implementar el archivado para Skype Empresarial Server.
  
El archivado se instala automáticamente en cada servidor front-end de la implementación de Skype Empresarial Server, pero debe realizar los pasos de configuración y configuración iniciales antes de poder usarlo. Antes de comenzar, asegúrese de que está familiarizado con los conceptos de [Plan for archiving in Skype Empresarial Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="deployment-checklist"></a>Lista de comprobación de implementación

La configuración del archivado depende de la opción de almacenamiento que elija: 
  
- Si usa la integración Exchange Microsoft para todos los usuarios de la implementación, no es necesario configurar las directivas de archivado Skype Empresarial Server para los usuarios. En su lugar, se configuran Exchange In-Place de retención para admitir el archivado para los usuarios que se alojen en Exchange, con sus buzones en In-Place retención. Para obtener más información sobre cómo configurar estas directivas, consulte la Exchange del producto.
    
- Si no usa la integración de Microsoft Exchange para todos los usuarios de la implementación, debe agregar bases de datos de archivado (bases de datos SQL Server) Skype Empresarial Server la topología, publicar la topología actualizada y, a continuación, configurar las directivas de archivado y la configuración de los usuarios. Puede implementar bases de datos de archivado al mismo tiempo que implementa la topología inicial o después de implementar al menos un grupo de servidores front-end o Standard Edition servidor. En este documento se describe cómo implementar bases de datos de archivado agregándolos a una implementación existente.
    
Si habilita el archivado en un grupo de servidores front-end o en un servidor Standard Edition, debe habilitarlo para todos los demás grupos de servidores front-end y servidores Standard Edition servidores de la implementación. Esto se debe a que los usuarios cuyas comunicaciones deben archivarse pueden ser invitados a una conversación de mensajería instantánea en grupo o a reuniones hospedadas en un grupo de servidores diferente. Si el archivado no está habilitado en el grupo donde se hospeda la conversación o reunión, es posible que no se archive la sesión completa. En estos casos, las IMs con usuarios habilitados para archivado aún se pueden archivar, pero no para archivos de contenido de conferencia, y eventos de unión o de conferencia.
  
> [!IMPORTANT]
> Si el archivado es fundamental en su organización por motivos de cumplimiento, asegúrese de implementar el archivado, configurar directivas y otras opciones en el nivel adecuado y, a continuación, activar el archivado para todos los usuarios adecuados, antes de habilitarlos para Skype Empresarial Server. 
  
En la tabla siguiente se proporciona información general sobre los pasos necesarios para implementar el archivado en una topología existente.
  
|**Fase**|**Pasos**|**Roles y pertenencia a grupos**|**Documentación**|
|:-----|:-----|:-----|:-----|
|**Instalar los requisitos previos de hardware y software** <br/> |Para usar la integración Exchange Microsoft (con Exchange para el almacenamiento de archivado para algunos o todos los usuarios), necesita una implementación Exchange cliente.  <br/> Para usar bases de datos de archivado independientes (SQL Server bases de datos de archivado) para el almacenamiento de archivado para algunos o todos los usuarios, SQL Server en el servidor que almacenará los datos de archivado.  <br/> El archivado se ejecuta en servidores front-end de un grupo Enterprise servidores Standard Edition servidores. No hay ningún requisito adicional de hardware o de software aparte de los necesarios para instalar dichos servidores.  <br/> |Usuario de dominio que es miembro del grupo de administradores locales.  <br/> |[Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisitos del entorno Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Plan para la integración de Skype Empresarial y Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Requisitos del sistema para Skype Empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Cree la topología interna adecuada para admitir el archivado (solo si no usa la integración de Microsoft Exchange para todos los usuarios de la implementación)** <br/> |Ejecute el Generador de topologías para agregar Skype Empresarial Server de archivado (SQL Server bases de datos) a la topología y, a continuación, publique la topología.  <br/> |Para definir una topología para incorporar bases de datos de archivado, una cuenta que sea miembro del grupo de usuarios locales.  <br/> Para publicar la topología, una cuenta que sea miembro del grupo de administradores de dominio y del grupo RTCUniversalServerAdmins y que tenga permisos de control total (lectura/escritura/modificación) en el recurso compartido de archivos que se usará para el almacén de archivos de Skype Empresarial Server (para que el Generador de topologías pueda configurar las DACL necesarias).  <br/> |[Agregar bases de datos de archivado a una implementación existente en Skype Empresarial Server](add-archiving-databases.md) <br/> |
|**Configurar la autenticación de servidor a servidor (solo si se usa microsoft Exchange integración)** <br/> |Configure los servidores para habilitar la autenticación entre Skype Empresarial Server y Exchange. Se recomienda ejecutar **Test-CsExchangeStorageConnectivity testuser_sipUri -Folder Dumpster** para validar Exchange de almacenamiento de archivado antes de habilitar el archivado. <br/> |Una cuenta con los permisos adecuados para administrar certificados en los servidores.  <br/> |Administrar la autenticación de servidor a servidor  <br/> |
|**Configurar directivas y opciones de archivado** <br/> |Configure el archivado, incluida la integración de Microsoft Exchange, la directiva global y las directivas de sitio y usuario (cuando no se usa la integración de Microsoft Exchange para todo el almacenamiento de datos) y opciones de archivado específicas, como el modo crítico y la exportación y depuración de datos.  <br/> Si usa microsoft Exchange integración, configure Exchange In-Place de retención según corresponda.  <br/> |Grupo RTCUniversalServerAdmins (solo Windows PowerShell) o asigne usuarios al rol CSArchivingAdministrator o CSAdministrator.  <br/> |[Configurar opciones de archivado para Skype Empresarial Server](configure-archiving-options.md) <br/> Exchange documentación del producto (si usa Microsoft Exchange integración).  <br/> |
   

