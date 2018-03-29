---
title: Implementaciones locales de bosques múltiples de Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de varios bosques.
ms.openlocfilehash: b5a0a2615f8174ea5e7d56dcaf0830765365bb48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="8d9cf-103">Implementaciones locales de bosques múltiples de Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="8d9cf-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="8d9cf-104">Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de varios bosques.</span><span class="sxs-lookup"><span data-stu-id="8d9cf-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8d9cf-105">Para implementar en varios bosques, sistema de sala de Skype requiere Exchange Server 2013 CU6 lanzado el 26 de agosto de 2014.</span><span class="sxs-lookup"><span data-stu-id="8d9cf-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="8d9cf-106">Evite volver a utilizar un buzón existente para el sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="8d9cf-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="8d9cf-107">Utilice un nuevo (eliminar el buzón antiguo y volver a crear) el buzón de recursos para el sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="8d9cf-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="8d9cf-108">Para restaurar las reuniones perdidas por eliminar el buzón, consulte [Conectar o restaurar un buzón eliminado](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="8d9cf-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="8d9cf-109">Después de crear el buzón, puede usar Set-CalendarProcessing para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="8d9cf-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="8d9cf-110">Consulte los pasos 3 a 6 de Implementaciones locales de un solo bosque para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="8d9cf-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="8d9cf-111">Después de crear un buzón de recursos de Exchange para el sistema de sala de Skype, habilite la cuenta de Skype para el negocio, siguiendo los pasos en cuentas del sistema habilitar sala Skype de Skype para el negocio en las implementaciones locales de bosque único.</span><span class="sxs-lookup"><span data-stu-id="8d9cf-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="8d9cf-112">Opción 1: crear un nuevo buzón de recursos</span><span class="sxs-lookup"><span data-stu-id="8d9cf-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="8d9cf-113">Implementar sistema de sala de Skype en un entorno de varios bosque:</span><span class="sxs-lookup"><span data-stu-id="8d9cf-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="8d9cf-114">Crear un usuario vinculado (LinkedRoomTest) en Active Directory (bosque de autenticación).</span><span class="sxs-lookup"><span data-stu-id="8d9cf-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="8d9cf-115">Ejecute los siguientes comandos en el Shell de administración de Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="8d9cf-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="8d9cf-116">Opción 2: Cambiar un buzón de sala existente al buzón de recursos (vinculados) del sistema de sala de Skype</span><span class="sxs-lookup"><span data-stu-id="8d9cf-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1

```


