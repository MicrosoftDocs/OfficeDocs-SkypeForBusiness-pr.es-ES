---
title: Configurar la integración con almacenamiento de Exchange para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar la integración con el almacenamiento de Exchange en Skype empresarial Server.'
ms.openlocfilehash: 72caf77c81dae538f793afe6f0a94ad6b61d0fa5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234334"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Configurar la integración con almacenamiento de Exchange para Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar la integración con el almacenamiento de Exchange en Skype empresarial Server.
  
Si usa la integración de Microsoft Exchange para todos los usuarios de su implementación, no es necesario que configure las directivas de archivado de Skype empresarial Server para los usuarios. En su lugar, puede configurar directivas de retención local de Exchange para admitir el archivado de usuarios alojados en Exchange, con sus buzones en conservación local. Antes de configurar la integración con el almacenamiento de Exchange, lea [Plan for archiving in Skype empresarial Server](../../plan-your-deployment/archiving/archiving.md). Para obtener más información sobre las directivas de retención local de Exchange, consulte la documentación del producto de Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurar la integración con el almacenamiento de Microsoft Exchange

1. Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.
    
4. Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado; haga clic en **Editar**, en **Mostrar detalles** y, luego, haga lo siguiente:
    
   - Para habilitar la integración con el almacenamiento de Exchange, active la casilla **integración con Microsoft Exchange** .
    
   - Para deshabilitar la integración con el almacenamiento de Exchange, desactive la casilla **integración con Microsoft Exchange** .
    
5. Haga clic en **Confirmar**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Cuando Skype empresarial Server y Microsoft Exchange se implementan en diferentes bosques

Si usa la integración de Microsoft Exchange y Microsoft Exchange Server no está implementado en el mismo bosque que Skype empresarial Server, debe asegurarse de que los siguientes atributos de Exchange Active Directory se sincronicen con el bosque en el que Skype para Se ha implementado Business Server:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Este es un atributo de varios valores. Al sincronizarlo, los valores se necesitan combinar, no reemplazar, para garantizar que no se pierdan los valores existentes.
  

