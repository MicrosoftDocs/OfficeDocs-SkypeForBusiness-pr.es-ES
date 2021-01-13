---
title: Configurar la integración con el almacenamiento de Exchange para Skype Empresarial Server
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
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumen: lea este tema para obtener información sobre cómo configurar la integración con el almacenamiento de Exchange en Skype Empresarial Server.'
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825070"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Configurar la integración con el almacenamiento de Exchange para Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar la integración con el almacenamiento de Exchange en Skype Empresarial Server.
  
Si usa la integración de Microsoft Exchange para todos los usuarios de su implementación, no es necesario configurar las directivas de archivado de Skype Empresarial Server para los usuarios. En su lugar, configure las directivas de retención de exchange In-Place para admitir el archivado para los usuarios que están en Exchange, con sus buzones de correo en In-Place retención. Antes de configurar la integración con el almacenamiento de Exchange, lea [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Para obtener más información sobre las directivas In-Place de retención de exchange, consulte la documentación del producto de Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurar la integración con el almacenamiento de Microsoft Exchange

1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.
    
4. Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada de la lista de configuraciones de archivado, en **Editar** y en **Mostrar detalles**. A continuación, haga lo siguiente:
    
   - Para habilitar la integración con el almacenamiento de Exchange, active la casilla **de verificación de integración** de Microsoft Exchange.
    
   - Para deshabilitar la integración con el almacenamiento de Exchange, desactive la casilla **de verificación de integración** de Microsoft Exchange.
    
5. Haga clic en **Confirmar**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Cuando Skype Empresarial Server y Microsoft Exchange se implementan en bosques diferentes

Si usa la integración de Microsoft Exchange y Microsoft Exchange Server no se implementa en el mismo bosque que Skype Empresarial Server, debe asegurarse de que los siguientes atributos de Exchange Active Directory se sincronizan con el bosque donde se implementa Skype Empresarial Server:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Este es un atributo de varios valores. Al sincronizar este atributo, debe combinar los valores, no reemplazarlos para asegurarse de que no se pierdan los valores existentes.
  

