---
title: Configurar la integración con el almacenamiento de Exchange de Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar la integración con el almacenamiento de Exchange en Skype para Business Server.'
ms.openlocfilehash: 35ef648a1076283f63752221a807da21bf4208ca
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370623"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Configurar la integración con el almacenamiento de Exchange de Skype para Business Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar la integración con el almacenamiento de Exchange en Skype para Business Server.
  
Si utiliza la integración de Microsoft Exchange para todos los usuarios de la implementación, no es necesario configurar Skype para las directivas de archivado para los usuarios de Business Server. En su lugar, configure las directivas de retención de Exchange local para admitir el archivado para los usuarios alojados en Exchange, con sus buzones poner en suspensión en contexto. Antes de configurar la integración con el almacenamiento de Exchange, lea [Plan for archiving en Skype para Business Server](../../plan-your-deployment/archiving/archiving.md). Para obtener información detallada sobre las directivas de retención de Exchange local, consulte la documentación de producto de Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurar la integración con el almacenamiento de información de Microsoft Exchange

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado; haga clic en **Editar**, en **Mostrar detalles** y, luego, haga lo siguiente:
    
   - Para habilitar la integración con el almacenamiento de Exchange, active la casilla de verificación de la **integración de Microsoft Exchange** .
    
   - Para deshabilitar la integración con el almacenamiento de Exchange, desactive la casilla de verificación de la **integración de Microsoft Exchange** .
    
5. Haga clic en **Confirmar**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Cuando se implementan Skype para Business Server y Microsoft Exchange en bosques diferentes

Si utiliza la integración de Microsoft Exchange y Microsoft Exchange Server no se ha implementado en el mismo bosque que Skype para Business Server, debe asegurarse de que se sincronizan los siguientes atributos de Active Directory de Exchange en el bosque donde Skype para Se implementa Business Server:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Este es un atributo de varios valores. Al sincronizarlo, los valores se necesitan combinar, no reemplazar, para garantizar que no se pierdan los valores existentes.
  

