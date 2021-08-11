---
title: Configurar la integración con Exchange almacenamiento para Skype Empresarial Server
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
description: 'Summary: Read this topic to learn how to configure integration with Exchange storage in Skype Empresarial Server.'
ms.openlocfilehash: e33c5fcfb4ff059a266abbd06f31674e753ba1efb16b094244cba4e1f333c098
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312098"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Configurar la integración con Exchange almacenamiento para Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar la integración con Exchange almacenamiento en Skype Empresarial Server.
  
Si usa la integración Exchange Microsoft para todos los usuarios de la implementación, no es necesario configurar las directivas de archivado Skype Empresarial Server para los usuarios. En su lugar, se configuran Exchange In-Place de retención para admitir el archivado para los usuarios que se alojen en Exchange, con sus buzones en In-Place retención. Antes de configurar la integración con Exchange almacenamiento, lea [Plan for archiving in Skype Empresarial Server](../../plan-your-deployment/archiving/archiving.md). Para obtener más información Exchange In-Place directivas de retención, consulte la Exchange del producto. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurar la integración con el almacenamiento Exchange Microsoft

1. Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 
    
3. En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.
    
4. Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada de la lista de configuraciones de archivado, en **Editar** y en **Mostrar detalles**. A continuación, haga lo siguiente:
    
   - Para habilitar la integración con Exchange almacenamiento, active la casilla de **Exchange integración de Microsoft.**
    
   - Para deshabilitar la integración con Exchange almacenamiento, desactive la casilla de **Exchange integración de Microsoft.**
    
5. Haga clic en **Confirmar**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Cuando Skype Empresarial Server y Microsoft Exchange se implementan en bosques diferentes

Si usa la integración de Microsoft Exchange y Microsoft Exchange Server no se implementa en el mismo bosque que Skype Empresarial Server, debe asegurarse de que los siguientes atributos de Exchange Active Directory estén sincronizados con el bosque donde se implementa Skype Empresarial Server:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Se trata de un atributo de varios valores. Al sincronizar este atributo, debe combinar los valores, no reemplazarlos para garantizar que no se pierdan los valores existentes.
  

