---
title: Skype de sala varias implementaciones locales de bosque
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Lea este tema para obtener información sobre cómo implementar Skype Room System en un entorno local de varios bosques.
ms.openlocfilehash: 45eef34f575144f720225a74d07efa0da2db30cd
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400744"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype de sala varias implementaciones locales de bosque
 
Lea este tema para obtener información sobre cómo implementar Skype Room System en un entorno local de varios bosques.
  
> [!NOTE]
> Para implementar en varios bosques, Skype Room System requiere Exchange Server 2013 CU6 publicado el 26 de agosto de 2014. Evite volver a usar un buzón existente para Skype room system. Use un buzón de recursos nuevo (eliminar buzón antiguo y volver a crear) para Skype room system. Para restaurar las reuniones perdidas mediante la eliminación del buzón, vea [Conectar o restaurar un buzón eliminado](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help). 
  
Después de crear el buzón, puede usar Set-CalendarProcessing para configurar el buzón. Consulte los pasos del 3 al 6 en Implementaciones locales de bosque único para obtener más información. Después de crear un buzón de recursos de Exchange para el sistema de sala de Skype, habilite la cuenta para Skype Empresarial siguiendo los pasos descritos en Habilitar cuentas del sistema de sala Skype para Skype Empresarial en Implementaciones locales de bosque único.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Opción 1: Crear un nuevo buzón de recursos

Para implementar Skype room system en un entorno de varios bosques:
  
1. Crear un usuario vinculado (LinkedRoomTest) en Active Directory (bosque de autenticación).
    
2. Ejecute los siguientes comandos en el Shell Exchange Server administración:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Opción 2: Cambiar un buzón de sala existente a Skype de recursos del sistema de sala (vinculado)

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```