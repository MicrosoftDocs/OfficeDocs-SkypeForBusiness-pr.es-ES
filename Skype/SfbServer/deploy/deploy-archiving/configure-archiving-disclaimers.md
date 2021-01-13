---
title: Configurar avisos de declinación de responsabilidades de archivado para usuarios externos en Skype Empresarial Server
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
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Resumen: lea este tema para obtener información sobre cómo configurar un aviso de declinación de responsabilidades de archivado para Skype Empresarial Server.'
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820670"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Configurar avisos de declinación de responsabilidades de archivado para usuarios externos en Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar un aviso de declinación de responsabilidades de archivado para Skype Empresarial Server.
  
Si su organización se comunica con socios externos, debe comunicarles que está archivando las comunicaciones con ellos. Al implementar un servidor perimetral y habilitar la federación para su organización, se le preguntará si desea enviar automáticamente un aviso de declinación de responsabilidades de archivado a socios externos. 
  
Si necesita cambiar esta configuración, puede usar el Panel de control de Skype Empresarial Server o el cmdlet **Windows PowerShell Set-CsAccessEdgeConfiguration.** Los cmdlets se pueden ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.
  
Para permitir que los usuarios externos colaboren con usuarios en su implementación de Skype Empresarial Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios externos. Para obtener más información, consulte Administrar socios federados XMPP para su organización. Para obtener más información sobre cómo controlar el acceso a dominios federados específicos, consulte Control access by Individual Federated Domains.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Habilitar o deshabilitar la declinación de responsabilidades de archivado con el Panel de control

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y luego en **Configuración perimetral de acceso**.
    
4. En la pestaña **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y en **Mostrar detalles**.
    
5. En **Editar** configuración perimetral de acceso, en Habilitar federación  y conectividad de mensajería instantánea **pública,** active o desactive la casilla Enviar declinación de responsabilidades de archivado a socios federados para habilitar o deshabilitar el envío automático del aviso de declinación de responsabilidades de archivado.
    
6. Haga clic en **Confirmar**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Habilitar o deshabilitar la declinación de responsabilidades de archivado mediante Windows PowerShell

Para habilitar la renuncia de archivado, establezca la propiedad **EnableArchivingDisclaimer** en True ($True):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Para deshabilitar la renuncia de archivado, establezca la propiedad **EnableArchivingDisclaimer** en False ($False):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


