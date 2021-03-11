---
title: Número de teléfono sinsignado Crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Los números sin asignar son números de teléfono válidos para su organización pero que no se han asignado a un usuario o teléfono. La tabla de números sin asignar identifica cómo desea que se traten las llamadas a números sin asignar.
ms.openlocfilehash: 51c3f640bd9d98bcda9d5dd69406461e9c8393fd
ms.sourcegitcommit: c477aa1a7da0b6b9bea1f5d10f1395eef418bfdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711747"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="c0b3f-104">Número de teléfono sin asignar: Crear nuevos o editar los existentes</span><span class="sxs-lookup"><span data-stu-id="c0b3f-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

<span data-ttu-id="c0b3f-p102">Los números sin asignar son números de teléfono válidos para su organización pero que no se han asignado a un usuario o teléfono. La tabla de números sin asignar identifica cómo desea que se traten las llamadas a números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0b3f-p103">Cuando termine de crear un nuevo intervalo numérico sin asignar o de editar uno existente, haga clic en **Aceptar** para volver a la página **Número no asignado**, que muestra todos los intervalos numéricos. Los cambios que realice en la página **Nuevo intervalo numérico sin asignar** o en la página **Editar intervalo numérico sin asignar** no se confirman en la base de datos hasta que no haga clic en **Confirmar todo** en la página **Número no asignado**.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-p103">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges. The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c0b3f-109">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c0b3f-109">UI Reference</span></span>

<span data-ttu-id="c0b3f-110">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c0b3f-111">**Nombre** Escriba un nombre descriptivo que identifique el intervalo de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="c0b3f-112">Una vez que guarde el intervalo, el nombre no se podrá cambiar.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-112">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="c0b3f-113">**Intervalo de números** En el primer campo, escriba el número inicial del intervalo de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="c0b3f-114">En el segundo campo, escriba el número de finalización del intervalo.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-114">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="c0b3f-115">El número inicial del intervalo debe ser menor o igual al número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="c0b3f-116">Si el número inicial o final del intervalo incluye un número de extensión, ambos números del intervalo deben incluir la extensión y el número de extensión debe ser igual al número inicial y final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="c0b3f-117">El número debe coincidir con la expresión regular `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` .</span><span class="sxs-lookup"><span data-stu-id="c0b3f-117">The number must match the regular expression `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?`.</span></span> <span data-ttu-id="c0b3f-118">Esto significa que el número puede comenzar por la cadena (si no especifica la cadena que se agregará automáticamente), un signo más (+) y un dígito del 1 al `tel:` 9.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-118">This means the number may begin with the string `tel:` (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="c0b3f-119">El número de teléfono puede tener hasta 17 dígitos y puede estar seguido de una extensión en formato ";ext=número de extensión".</span><span class="sxs-lookup"><span data-stu-id="c0b3f-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="c0b3f-120">**Servicio de anuncios** Seleccione **Anuncio** para que la aplicación Anuncio controle la llamada entrante o la mensajería unificada de **Exchange** para que una mensajería unificada de Exchange Operador automático la llamada entrante.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="c0b3f-121">Si ha seleccionado **Anuncio** para el servicio **Anuncio**:</span><span class="sxs-lookup"><span data-stu-id="c0b3f-121">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="c0b3f-122">**FQDN del servidor de destino** Seleccione el identificador de servicio del servicio de aplicación que ejecuta la aplicación Anuncio que controlará las llamadas entrantes a este rango de números sinsignación.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="c0b3f-123">**Anuncio** Seleccione el anuncio que se va a reproducir para este intervalo de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="c0b3f-124">Si ha seleccionado **Mensajería unificada de Exchange** para el servicio **Anuncio**:</span><span class="sxs-lookup"><span data-stu-id="c0b3f-124">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="c0b3f-125">**Operador automático de teléfono** Seleccione el número de teléfono para la mensajería unificada de Exchange Operador automático.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="c0b3f-126">Para obtener más información sobre las características y capacidades del anuncio, vea [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="c0b3f-127">Para obtener más detalles sobre cómo trabajar con rangos de números sin asignar, vea [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="c0b3f-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


