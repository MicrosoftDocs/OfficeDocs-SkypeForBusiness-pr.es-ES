---
title: Configurar declinaciones de responsabilidades de archivado para usuarios externos en Skype Empresarial Server
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
description: 'Resumen: lea este tema para obtener información sobre cómo configurar una declinación de responsabilidades de archivado para Skype Empresarial Server.'
ms.openlocfilehash: 1afacace566cc75659e5b53e05346461b99f0cb888497f79da6340130585c959
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312148"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Configurar declinaciones de responsabilidades de archivado para usuarios externos en Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar una declinación de responsabilidades de archivado para Skype Empresarial Server.
  
Si su organización se comunica con socios externos, debe comunicarles que está archivando las comunicaciones con ellos. Al implementar un servidor perimetral y habilitar la federación para la organización, se le pregunta si desea enviar automáticamente una declinación de responsabilidades de archivado a socios externos. 
  
Si necesita cambiar esta configuración, puede usar el Panel de control Skype Empresarial Server o el cmdlet **Set-CsAccessEdgeConfiguration** Windows PowerShell de configuración. Los cmdlets se pueden ejecutar desde el shell Skype Empresarial Server administración o desde una sesión remota de Windows PowerShell.
  
Para permitir que los usuarios externos colaboren con los usuarios en la implementación Skype Empresarial Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios externos. Para obtener más información, consulte Manage XMPP Federated Partners for Your Organization. Para obtener más información sobre cómo controlar el acceso para dominios federados específicos, vea Control Access by Individual Federated Domains.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Habilitar o deshabilitar la declinación de responsabilidades de archivado mediante el Panel de control

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 
    
3. En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y luego en **Configuración perimetral de acceso**.
    
4. En la pestaña **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y en **Mostrar detalles**.
    
5. En **Editar** configuración perimetral de acceso , en Habilitar  la federación y la conectividad de mensajería instantánea **pública,** active o desactive la casilla Enviar declinación de responsabilidades de archivado a socios federados para habilitar o deshabilitar el envío automático del aviso de declinación de responsabilidades de archivado.
    
6. Haga clic en **Confirmar**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Habilitar o deshabilitar la declinación de responsabilidades de archivado Windows PowerShell

Para habilitar la renuncia de archivado, establezca la propiedad **EnableArchivingDisclaimer** en True ($True):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Para deshabilitar la renuncia de archivado, establezca la propiedad **EnableArchivingDisclaimer** en False ($False):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


