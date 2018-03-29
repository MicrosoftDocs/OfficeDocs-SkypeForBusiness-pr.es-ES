---
title: Configurar la integración con el almacenamiento de Exchange para Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumen: Leer este tema para obtener información sobre cómo configurar la integración con almacenamiento de información de Exchange en Skype para Business Server 2015.'
ms.openlocfilehash: 2d814bb297999062aaf93160286031afec51c3a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server-2015"></a>Configurar la integración con el almacenamiento de Exchange para Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a configurar la integración con almacenamiento de información de Exchange en Skype para Business Server 2015.
  
Si utiliza la integración de Microsoft Exchange para todos los usuarios en la implementación, no es necesario configurar Skype para políticas de archiving Business Server para los usuarios. En su lugar, configurar directivas de Exchange en el mismo lugar mantenga para soportar archiving para usuarios alojados en Exchange, con sus buzones poner en posesión en el lugar. Antes de configurar la integración con el almacenamiento de información de Exchange, lea el [Plan para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md). Para obtener más información acerca de las directivas en colocar espera de Exchange, consulte la documentación del producto Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurar la integración con el almacenamiento de información de Microsoft Exchange

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado; haga clic en **Editar**, en **Mostrar detalles** y, luego, haga lo siguiente:
    
  - Para habilitar la integración con el almacenamiento de información de Exchange, active la casilla de verificación de **integración de Microsoft Exchange** .
    
  - Para deshabilitar la integración con el almacenamiento de información de Exchange, desactive la casilla de verificación de la **integración de Microsoft Exchange** .
    
5. Haga clic en **Confirmar**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Cuando se implementan Skype para Business Server y Microsoft Exchange en bosques diferentes

Si utiliza la integración de Microsoft Exchange y Microsoft Exchange Server no se implementa en el mismo bosque que Skype para Business Server, debe asegurarse de que los siguientes atributos de Active Directory de Exchange están sincronizados con el bosque donde Skype para Business Server está implementado:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Este es un atributo de varios valores. Al sincronizarlo, los valores se necesitan combinar, no reemplazar, para garantizar que no se pierdan los valores existentes.
  

