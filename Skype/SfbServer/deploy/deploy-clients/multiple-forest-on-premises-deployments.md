---
title: Implementaciones locales de bosques múltiples de Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de varios bosques.
ms.openlocfilehash: 607177a1b091fb4d7872b726fa31cd0329b3b975
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895043"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Implementaciones locales de bosques múltiples de Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de varios bosques.
  
> [!NOTE]
> Para implementar en varios bosques, sistema de sala de Skype requiere Exchange Server 2013 CU6 publicado en 26 de agosto de 2014. Evitar el uso de volver a un buzón existente para el sistema de sala de Skype. Usar un nuevo (eliminar el buzón antiguo y volver a crear) buzón de recursos para el sistema de sala de Skype. Para restaurar las reuniones perdidas, elimine el buzón de correo, vea [Conectar o restaurar un buzón eliminado](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Después de crear el buzón, puede usar Set-CalendarProcessing para configurarlo. Consulte los pasos 3 a 6 de Implementaciones locales de un solo bosque para obtener más detalles. Después de crear un buzón de recursos de Exchange para el sistema de sala de Skype, habilite la cuenta de Skype para la empresa siguiendo los pasos de habilitación de las cuentas del sistema de sala de Skype para Skype para la empresa en las implementaciones locales de bosque único.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Opción 1: crear un nuevo buzón de recursos

Para implementar el sistema de sala de Skype en un entorno de varios bosque:
  
1. Crear un usuario vinculado (LinkedRoomTest) en Active Directory (bosque de autenticación).
    
2. Ejecute los siguientes comandos en el Shell de administración de Exchange Server:
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Opción 2: Cambiar un buzón de sala existente al buzón de recurso (vinculado) del sistema de sala de Skype

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


