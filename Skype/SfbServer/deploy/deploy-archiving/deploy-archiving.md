---
title: Implementar el archivado de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Resumen: Lea este tema para obtener información sobre cómo implementar el archivado en Skype empresarial Server.'
ms.openlocfilehash: c4f0e28c0b48cc93f1c03296f6d00555d1a7d327
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769123"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Implementar el archivado de Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo implementar el archivado en Skype empresarial Server.
  
El archivado se instala automáticamente en cada servidor front-end de su implementación de Skype empresarial Server, pero es necesario realizar los pasos iniciales de configuración para poder usarlo. Antes de empezar, asegúrese de que está familiarizado con los conceptos de [planeación del archivado en Skype empresarial Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="deployment-checklist"></a>Lista de comprobación de la implementación

La configuración de archivado depende de la opción de almacenamiento que elija: 
  
- Si usa la integración de Microsoft Exchange para todos los usuarios de su implementación, no es necesario que configure las directivas de archivado de Skype empresarial Server para los usuarios. En su lugar, puede configurar directivas de retención local de Exchange para admitir el archivado de usuarios alojados en Exchange, con sus buzones en conservación local. Para obtener más información sobre cómo configurar estas directivas, consulte la documentación del producto de Exchange.
    
- Si no usa la integración de Microsoft Exchange para todos los usuarios de su implementación, debe agregar bases de datos de archivado de Skype empresarial Server (bases de datos de SQL Server) a su topología, publicar la topología actualizada y, a continuación, configurar las directivas de archivado y configuración para los usuarios. Puede implementar bases de datos de archivado a la vez que implementa la topología inicial o después de implementar, como mínimo, un grupo de servidores front-end o un servidor Standard Edition. En este documento se describe cómo implementar bases de datos de archivado agregándolas a una implementación existente.
    
Si habilita el archivado en un grupo de servidores front-end o en un servidor Standard Edition, será necesario que lo habilite para todos los demás grupos de servidores de front-end y los servidores Standard Edition de su implementación, ya que los usuarios cuyas comunicaciones se tienen que archivar pueden ser invitados a una conversación de mensajería instantánea (MI) en grupo o a reuniones hospedadas en un grupo de servidores diferente. Si el archivado no está habilitado en el grupo de servidores donde se hospeda la conversación o la reunión, puede que no se almacene toda la sesión. En estos casos, se podrán seguir archivando los mensajes instantáneos de los usuarios que tengan habilitado el archivado, pero no los archivos de contenido de conferencias ni los eventos creados al unirse a conferencias o abandonarlas.
  
> [!IMPORTANT]
> Si el archivado es importante en su organización por razones de cumplimiento, asegúrese de implementar el archivado, configurar directivas y otras opciones en el nivel correspondiente y, después, activar el archivado de todos los usuarios apropiados, antes de habilitar a esos usuarios para Skype para Business Server. 
  
La tabla siguiente proporciona información general de los pasos necesarios para implementar el archivado en una topología existente.
  
|**Fase**|**Pasos**|**Roles y pertenencias a grupos**|**Documentación**|
|:-----|:-----|:-----|:-----|
|**Instalar los requisitos previos de hardware y software** <br/> |Para usar la integración de Microsoft Exchange (con Exchange para archivar el almacenamiento para algunos o todos los usuarios), necesita una implementación existente de Exchange.  <br/> Para usar bases de datos independientes (con bases de datos de SQL Server) para el almacén de archivado para algunos o todos los usuarios, necesitará SQL Server en el servidor que almacenará los datos de archivado.  <br/> El archivado se ejecuta en servidores front-end de un grupo de servidores Enterprise y en servidores Standard Edition. No hay ningún requisito adicional de hardware o de software aparte de los necesarios para instalar dichos servidores.  <br/> |Usuario de dominio que es miembro del grupo de administradores locales.  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Plan para la integración de Skype Empresarial y Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Requisitos del sistema para Skype empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Crear la topología interna adecuada para admitir el archivado (solo si no se usa la integración de Microsoft Exchange para todos los usuarios de la implementación)** <br/> |Ejecute el generador de topologías para agregar bases de datos de archivado de Skype empresarial Server (bases de datos de SQL Server) a la topología y, después, publique la topología.  <br/> |A fin de definir una topología para incorporar bases de datos de archivado, se necesita una cuenta que pertenezca al grupo de usuarios locales.  <br/> Para publicar la topología, una cuenta que sea miembro del grupo administradores del dominio y del grupo RTCUniversalServerAdmins, y que tenga permisos de control total (lectura/escritura/modificación) en el recurso compartido de archivos para el almacén de archivos de Skype empresarial Server (para que topología pueda configurar las DACL requeridas).  <br/> |[Agregar bases de datos de archivado a una implementación existente en Skype empresarial Server](add-archiving-databases.md) <br/> |
|**Configurar la autenticación de servidor a servidor (solo si se usa la integración de Microsoft Exchange)** <br/> |Configure servidores para habilitar la autenticación entre Skype empresarial Server y Exchange. Le recomendamos que ejecute **Test-CsExchangeStorageConnectivity testuser_sipUri-contenedor de carpetas** para validar la Conectividad del almacenamiento de archivado de Exchange antes de habilitar el archivado. <br/> |Una cuenta con los permisos necesarios para administrar certificados en los servidores.  <br/> |Administrar la autenticación de servidor a servidor  <br/> |
|**Configurar las opciones de archivado y las directivas** <br/> |Configurar el archivado, incluyendo si se debe usar la integración de Microsoft Exchange, la directiva global y las directivas de sitio y de usuario (si no se usa la integración de Microsoft Exchange para todo el almacenamiento de datos) y opciones de archivado específicas, como los datos y el modo crítico exportar y purgar.  <br/> Si usa la integración de Microsoft Exchange, configure las directivas de retención local de Exchange según corresponda.  <br/> |Grupo RTCUniversalServerAdmins (solo Windows PowerShell) o asigne los usuarios al rol CSArchivingAdministrator o CSAdministrator.  <br/> |[Configurar opciones de archivado para Skype empresarial Server](configure-archiving-options.md) <br/> Documentación de producto de Exchange (si se usa la integración de Microsoft Exchange).  <br/> |
   

