---
title: Implementaciones locales de varios bosques del Sistema de sala de Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Lea este tema para obtener información sobre cómo implementar el Sistema de sala de Skype en un entorno local de varios bosques.
ms.openlocfilehash: 168244033a681b9aa9dc6e4c9697b7e3c7e89127
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805750"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Implementaciones locales de varios bosques del Sistema de sala de Skype
 
Lea este tema para obtener información sobre cómo implementar el Sistema de sala de Skype en un entorno local de varios bosques.
  
> [!NOTE]
> Para implementar en varios bosques, El Sistema de sala de Skype requiere Exchange Server 2013 CU6 publicado el 26 de agosto de 2014. Evite volver a usar un buzón existente para el Sistema de sala de Skype. Use un nuevo buzón de recursos (elimine el buzón antiguo y vuelva a crearlo) para el Sistema de sala de Skype. Para restaurar las reuniones perdidas eliminando el buzón, consulte [Conectar o restaurar un buzón eliminado.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx) 
  
Después de crear el buzón, puede usar Set-CalendarProcessing para configurar el buzón. Consulte los pasos del 3 al 6 en Implementaciones locales de bosque único para obtener más información. After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Opción 1: Crear un nuevo buzón de recursos

Para implementar el Sistema de sala de Skype en un entorno de varios bosques:
  
1. Crear un usuario vinculado (LinkedRoomTest) en Active Directory (bosque de autenticación).
    
2. Ejecute los comandos siguientes en el Shell Exchange Server administración de contenido:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Opción 2: Cambiar un buzón de sala existente al buzón de recursos del Sistema de sala de Skype (vinculado)

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


