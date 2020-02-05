---
title: Implementaciones locales de bosques múltiples de Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de varios bosques.
ms.openlocfilehash: ac9a5edac94d182812aefaf9eb817765c7af6444
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768823"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Implementaciones locales de bosques múltiples de Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de varios bosques.
  
> [!NOTE]
> Para poder realizar la implementación en varios bosques, el sistema de salas de Skype requiere Exchange Server 2013 CU6 publicado el 26 de agosto de 2014. Evita volver a usar un buzón existente para el sistema de salas de Skype. Use un buzón de recursos nuevo (eliminar antiguo buzón y volver a crear) para el sistema de salas de Skype. Para restaurar las reuniones perdidas eliminando el buzón de correo, vea [conectar o restaurar un buzón eliminado](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Después de crear el buzón, puede usar Set-CalendarProcessing para configurarlo. Consulte los pasos 3 a 6 de Implementaciones locales de un solo bosque para obtener más detalles. Después de crear un buzón de recursos de Exchange para el sistema de salas de Skype, habilite la cuenta de Skype empresarial siguiendo los pasos que se indican en habilitar las cuentas del sistema de salas de Skype para Skype empresarial en implementaciones locales de bosque único.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Opción 1: crear un nuevo buzón de recursos

Para implementar el sistema de salas de Skype en un entorno de varios bosques:
  
1. Crear un usuario vinculado (LinkedRoomTest) en Active Directory (bosque de autenticación).
    
2. Ejecute los siguientes comandos en el Shell de administración de Exchange Server:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Opción 2: cambiar un buzón de sala existente a buzón de recursos de sistema de sala de Skype (vinculado)

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


