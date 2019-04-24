---
title: Implementaciones locales de bosques múltiples de Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de varios bosques.
ms.openlocfilehash: 507040a1d8274817e7a4a0780135ee8f6642c77c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219419"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="e63e2-103">Implementaciones locales de bosques múltiples de Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="e63e2-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="e63e2-104">Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de varios bosques.</span><span class="sxs-lookup"><span data-stu-id="e63e2-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e63e2-105">Para implementar en varios bosques, sistema de sala de Skype requiere Exchange Server 2013 CU6 publicado en 26 de agosto de 2014.</span><span class="sxs-lookup"><span data-stu-id="e63e2-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="e63e2-106">Evitar el uso de volver a un buzón existente para el sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="e63e2-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="e63e2-107">Usar un nuevo (eliminar el buzón antiguo y volver a crear) buzón de recursos para el sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="e63e2-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="e63e2-108">Para restaurar las reuniones perdidas, elimine el buzón de correo, vea [Conectar o restaurar un buzón eliminado](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e63e2-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="e63e2-109">Después de crear el buzón, puede usar Set-CalendarProcessing para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="e63e2-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="e63e2-110">Consulte los pasos 3 a 6 de Implementaciones locales de un solo bosque para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="e63e2-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="e63e2-111">Después de crear un buzón de recursos de Exchange para el sistema de sala de Skype, habilite la cuenta de Skype para la empresa siguiendo los pasos de habilitación de las cuentas del sistema de sala de Skype para Skype para la empresa en las implementaciones locales de bosque único.</span><span class="sxs-lookup"><span data-stu-id="e63e2-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="e63e2-112">Opción 1: crear un nuevo buzón de recursos</span><span class="sxs-lookup"><span data-stu-id="e63e2-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="e63e2-113">Para implementar el sistema de sala de Skype en un entorno de varios bosque:</span><span class="sxs-lookup"><span data-stu-id="e63e2-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="e63e2-114">Crear un usuario vinculado (LinkedRoomTest) en Active Directory (bosque de autenticación).</span><span class="sxs-lookup"><span data-stu-id="e63e2-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="e63e2-115">Ejecute los siguientes comandos en el Shell de administración de Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="e63e2-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="e63e2-116">Opción 2: Cambiar un buzón de sala existente al buzón de recurso (vinculado) del sistema de sala de Skype</span><span class="sxs-lookup"><span data-stu-id="e63e2-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


