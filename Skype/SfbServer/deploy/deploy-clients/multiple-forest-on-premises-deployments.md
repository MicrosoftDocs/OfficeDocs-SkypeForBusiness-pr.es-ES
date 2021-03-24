---
title: Sistema de salón de Skype con varias implementaciones locales de bosque
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
description: Lea este tema para obtener información sobre cómo implementar Skype Room System en un entorno local de varios bosques.
ms.openlocfilehash: d215ce13059c414d6c6142d7cd1e93ea9011c97b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093534"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="b9d2b-103">Sistema de salón de Skype con varias implementaciones locales de bosque</span><span class="sxs-lookup"><span data-stu-id="b9d2b-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="b9d2b-104">Lea este tema para obtener información sobre cómo implementar Skype Room System en un entorno local de varios bosques.</span><span class="sxs-lookup"><span data-stu-id="b9d2b-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9d2b-105">Para implementar en varios bosques, Skype Room System requiere Exchange Server 2013 CU6 publicado el 26 de agosto de 2014.</span><span class="sxs-lookup"><span data-stu-id="b9d2b-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="b9d2b-106">Evite volver a usar un buzón existente para el sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="b9d2b-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="b9d2b-107">Use un buzón de recursos nuevo (eliminar buzón antiguo y volver a crear) para el sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="b9d2b-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="b9d2b-108">Para restaurar las reuniones perdidas mediante la eliminación del buzón, vea [Conectar o restaurar un buzón eliminado.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="b9d2b-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help).</span></span> 
  
<span data-ttu-id="b9d2b-109">Después de crear el buzón, puede usar Set-CalendarProcessing para configurar el buzón.</span><span class="sxs-lookup"><span data-stu-id="b9d2b-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="b9d2b-110">Consulte los pasos del 3 al 6 en Implementaciones locales de bosque único para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b9d2b-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="b9d2b-111">Después de crear un buzón de recursos de Exchange para el sistema de sala de Skype, habilite la cuenta de Skype Empresarial siguiendo los pasos descritos en Habilitar cuentas de sistema de salón de Skype Empresarial en Implementaciones locales de bosque único.</span><span class="sxs-lookup"><span data-stu-id="b9d2b-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="b9d2b-112">Opción 1: Crear un nuevo buzón de recursos</span><span class="sxs-lookup"><span data-stu-id="b9d2b-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="b9d2b-113">Para implementar el sistema de salón de Skype en un entorno de varios bosques:</span><span class="sxs-lookup"><span data-stu-id="b9d2b-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="b9d2b-114">Crear un usuario vinculado (LinkedRoomTest) en Active Directory (bosque de autenticación).</span><span class="sxs-lookup"><span data-stu-id="b9d2b-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="b9d2b-115">Ejecute los siguientes comandos en el Shell Exchange Server administración:</span><span class="sxs-lookup"><span data-stu-id="b9d2b-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="b9d2b-116">Opción 2: Cambiar un buzón de sala existente al buzón de recursos del Sistema de sala de Skype (vinculado)</span><span class="sxs-lookup"><span data-stu-id="b9d2b-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```