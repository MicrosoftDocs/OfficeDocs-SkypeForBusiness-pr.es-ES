---
title: Implementar el archivado para Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Resumen: Leer este tema para aprender a implementar archiving de Skype para Business Server 2015.'
ms.openlocfilehash: d218c59038b599f016f99cbce453f0bf1830a6f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-archiving-for-skype-for-business-server-2015"></a>Implementar el archivado para Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a implementar archiving de Skype para Business Server 2015.
  
Archivado se instala automáticamente en cada servidor Front-End en su Skype para la implementación de Business Server 2015, pero todavía debe realizar la configuración inicial y los pasos de configuración antes de que pueda utilizar. Antes de comenzar, asegúrese de que está familiarizado con los conceptos de [Plan para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="deployment-checklist"></a>Lista de comprobación de la implementación

La configuración de archivado depende de la opción de almacenamiento que elija: 
  
- Si utiliza la integración de Microsoft Exchange para todos los usuarios en la implementación, no es necesario configurar Skype para políticas de archiving Business Server para los usuarios. En su lugar, configurar directivas de Exchange en el mismo lugar mantenga para soportar archiving para usuarios alojados en Exchange, con sus buzones poner en posesión en el lugar. Para obtener más información acerca de cómo configurar estas directivas, consulte la documentación del producto Exchange.
    
- Si no utiliza la integración de Microsoft Exchange para todos los usuarios en la implementación, necesita agregar Skype para Business Server archivar bases de datos (bases de datos de SQL Server) a la topología, publica la topología actualizados y, a continuación, configurar las políticas de archiving y configuración de los usuarios. Puede implementar bases de datos de archivado a la vez que implementa la topología inicial o después de implementar, como mínimo, un grupo de servidores front-end o un servidor Standard Edition. En este documento se describe cómo implementar bases de datos de archivado agregándolas a una implementación existente.
    
Si habilita el archivado en un grupo de servidores front-end o en un servidor Standard Edition, será necesario que lo habilite para todos los demás grupos de servidores de front-end y los servidores Standard Edition de su implementación, ya que los usuarios cuyas comunicaciones se tienen que archivar pueden ser invitados a una conversación de mensajería instantánea (MI) en grupo o a reuniones hospedadas en un grupo de servidores diferente. Si el archivado no está habilitado en el grupo de servidores donde se hospeda la conversación o la reunión, puede que no se almacene toda la sesión. En estos casos, se podrán seguir archivando los mensajes instantáneos de los usuarios que tengan habilitado el archivado, pero no los archivos de contenido de conferencias ni los eventos creados al unirse a conferencias o abandonarlas.
  
> [!IMPORTANT]
> Si es crítico en su organización, por razones de cumplimiento de normas de archiving, asegúrese de implementar archiving, configurar directivas y otras opciones en el nivel apropiado y, a continuación, activa el archivo para todos los usuarios adecuados, antes de habilitar a los usuarios de Skype para Business Server. 
  
La tabla siguiente proporciona información general de los pasos necesarios para implementar el archivado en una topología existente.
  
|**Fase**|**Pasos**|**Funciones y pertenencias a grupos**|**Documentación**|
|:-----|:-----|:-----|:-----|
|**Instalar los requisitos previos de hardware y software** <br/> |Para utilizar la integración de Microsoft Exchange (usando Exchange para el almacenamiento de archiving para algunos o todos los usuarios), necesita una implementación de Exchange existente.  <br/> Para usar bases de datos independientes (con bases de datos de SQL Server) para el almacén de archivado para algunos o todos los usuarios, necesitará SQL Server en el servidor que almacenará los datos de archivado.  <br/> El archivado se ejecuta en servidores front-end de un grupo de servidores Enterprise y en servidores Standard Edition. No hay ningún requisito adicional de hardware o de software aparte de los necesarios para instalar dichos servidores.  <br/> |Usuario de dominio que es miembro del grupo de administradores locales.  <br/> |[Requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisitos ambientales para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Requisitos de hardware y software para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/hardware-and-software-requirements.md) <br/> [Planear la integración de Skype para empresas y Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/> |
|**Crear la topología interna adecuada para soportar archiving (sólo si no mediante la integración de Microsoft Exchange para todos los usuarios en la implementación)** <br/> |Ejecutar el generador de topología para agregar Skype para Business Server archivar bases de datos (bases de datos de SQL Server) a la topología y, a continuación, publicar la topología.  <br/> |A fin de definir una topología para incorporar bases de datos de archivado, se necesita una cuenta que pertenezca al grupo de usuarios locales.  <br/> Para publicar la topología, una cuenta que sea miembro del grupo Administradores de dominio y grupo RTCUniversalServerAdmins y que tiene permisos de control total (lectura/escritura/modificación) en el recurso compartido de archivo que se utilizará para el Skype para el almacén de archivos de Business Server (para que topología Generador puede configurar las DACL necesarias).  <br/> |[Agregar bases de datos de archiving a una implementación existente de Skype para Business Server 2015](add-archiving-databases.md) <br/> |
|**Configurar la autenticación de servidor a servidor (sólo si utiliza la integración de Microsoft Exchange)** <br/> |Configurar servidores para habilitar la autenticación entre Skype para Business Server y Exchange. Se recomienda ejecutar **testuser_sipUri de CsExchangeStorageConnectivity de prueba-carpeta contenedor** para validar la conectividad de almacenamiento de archiving antes de habilitar el archivado de Exchange. <br/> |Una cuenta con los permisos necesarios para administrar certificados en los servidores.  <br/> |Administrar la autenticación de servidor a servidor  <br/> |
|**Configurar las opciones de archivado y las directivas** <br/> |Configurar el archivado, incluyendo si se va a utilizar la integración de Microsoft Exchange, la directiva global y las directivas de usuario y sitio (cuando no mediante la integración de Microsoft Exchange para todo el almacenamiento de datos) y específico de archiving opciones, como el modo crítico y datos exportación y la limpieza.  <br/> Si utiliza la integración de Microsoft Exchange, configurar directivas de Exchange en el mismo lugar mantenga según corresponda.  <br/> |Grupo RTCUniversalServerAdmins (solo Windows PowerShell) o asigne los usuarios al rol CSArchivingAdministrator o CSAdministrator.  <br/> |[Configurar opciones de archivado de Skype para Business Server 2015](configure-archiving-options.md) <br/> Documentación del producto de Exchange (si utiliza la integración de Microsoft Exchange).  <br/> |
   

