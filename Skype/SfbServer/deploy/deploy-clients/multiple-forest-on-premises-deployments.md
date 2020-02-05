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
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="106c9-103">Implementaciones locales de bosques múltiples de Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="106c9-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="106c9-104">Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de varios bosques.</span><span class="sxs-lookup"><span data-stu-id="106c9-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="106c9-105">Para poder realizar la implementación en varios bosques, el sistema de salas de Skype requiere Exchange Server 2013 CU6 publicado el 26 de agosto de 2014.</span><span class="sxs-lookup"><span data-stu-id="106c9-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="106c9-106">Evita volver a usar un buzón existente para el sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="106c9-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="106c9-107">Use un buzón de recursos nuevo (eliminar antiguo buzón y volver a crear) para el sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="106c9-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="106c9-108">Para restaurar las reuniones perdidas eliminando el buzón de correo, vea [conectar o restaurar un buzón eliminado](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="106c9-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="106c9-109">Después de crear el buzón, puede usar Set-CalendarProcessing para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="106c9-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="106c9-110">Consulte los pasos 3 a 6 de Implementaciones locales de un solo bosque para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="106c9-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="106c9-111">Después de crear un buzón de recursos de Exchange para el sistema de salas de Skype, habilite la cuenta de Skype empresarial siguiendo los pasos que se indican en habilitar las cuentas del sistema de salas de Skype para Skype empresarial en implementaciones locales de bosque único.</span><span class="sxs-lookup"><span data-stu-id="106c9-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="106c9-112">Opción 1: crear un nuevo buzón de recursos</span><span class="sxs-lookup"><span data-stu-id="106c9-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="106c9-113">Para implementar el sistema de salas de Skype en un entorno de varios bosques:</span><span class="sxs-lookup"><span data-stu-id="106c9-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="106c9-114">Crear un usuario vinculado (LinkedRoomTest) en Active Directory (bosque de autenticación).</span><span class="sxs-lookup"><span data-stu-id="106c9-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="106c9-115">Ejecute los siguientes comandos en el Shell de administración de Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="106c9-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="106c9-116">Opción 2: cambiar un buzón de sala existente a buzón de recursos de sistema de sala de Skype (vinculado)</span><span class="sxs-lookup"><span data-stu-id="106c9-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


