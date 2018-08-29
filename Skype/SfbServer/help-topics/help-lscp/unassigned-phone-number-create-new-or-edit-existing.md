---
title: Número de teléfono sin asignar crear nuevos o editar los existentes
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.
ms.openlocfilehash: 8983c52691eec7945f431be3efdce56be025ee6b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261409"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="9fd6d-104">Número de teléfono sin asignar: Crear nuevos o editar los existentes</span><span class="sxs-lookup"><span data-stu-id="9fd6d-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

<span data-ttu-id="9fd6d-p102">Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9fd6d-107">Cuando haya terminado de crear un nuevo intervalo numérico sin asignar o modificar uno existente, haga clic en **Aceptar** para volver a la página **Número sin asignar** que se enumera todos los intervalos de números.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-107">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="9fd6d-108">Los cambios realizados en la página **Nuevo Unassigned Number Range** o en la página **Editar Rage de número sin asignar** no se confirman en la base de datos hasta que haga clic en **Confirmar todo** en la página **Número sin asignar** .</span><span class="sxs-lookup"><span data-stu-id="9fd6d-108">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="9fd6d-109">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="9fd6d-109">UI Reference</span></span>

<span data-ttu-id="9fd6d-110">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="9fd6d-111">**Nombre** Escriba un nombre descriptivo que identifica el intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="9fd6d-112">Después de guardar el intervalo, no se puede cambiar este nombre.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-112">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="9fd6d-113">**Intervalo de número** En el primer campo, escriba el número inicial del intervalo numérico sin asignar.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="9fd6d-114">En el segundo campo, escriba el número final del rango.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-114">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="9fd6d-115">El número inicial del intervalo debe ser menor o igual al número final.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="9fd6d-116">Si el número inicial o final del intervalo incluye un número de extensión, ambos números del intervalo deben incluir la extensión y el número de extensión debe ser igual al número inicial y final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="9fd6d-117">El número debe coincidir con la expresión regular (tel:) ? (\+) ? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-117">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="9fd6d-118">Esto significa que el número de puede comenzar con la cadena tel: (si no se especifica esa cadena se agregará automáticamente para usted), un signo más (+) y un dígito del 1 al 9.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-118">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="9fd6d-119">El número de teléfono puede tener hasta 17 dígitos y puede estar seguido de una extensión en formato ";ext=número de extensión".</span><span class="sxs-lookup"><span data-stu-id="9fd6d-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="9fd6d-120">**Servicio de anuncio** Seleccione el **anuncio** para que la aplicación de anuncio controlar la llamada entrante o **Mensajería unificada de Exchange** para tener un operador de Exchange UM automático controlar la llamada entrante.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="9fd6d-121">Si ha seleccionado **anuncio** para **el servicio de anuncio**:</span><span class="sxs-lookup"><span data-stu-id="9fd6d-121">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="9fd6d-122">**FQDN del servidor de destino** Seleccione el identificador de servicio de la aplicación que se ejecuta la aplicación de anuncio que controlará las llamadas entrantes a este intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="9fd6d-123">**Anuncio** Seleccione el anuncio se reproducirá para este intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

-  <span data-ttu-id="9fd6d-124">Si ha seleccionado **Mensajería unificada de Exchange** para **el servicio de anuncio**:</span><span class="sxs-lookup"><span data-stu-id="9fd6d-124">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="9fd6d-125">**Número de teléfono del operador automático** Seleccione el número de teléfono para el operador de Exchange UM automático.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="9fd6d-126">Para obtener información detallada sobre las capacidades y características de anuncio, consulte [Plan para la aplicación de anuncio en Skype para 2015 empresarial](../../plan-your-deployment/enterprise-voice-solution/announcement.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="9fd6d-127">Para obtener información detallada sobre cómo trabajar con intervalos numéricos sin asignar, vea [Configurar el enrutamiento de sin asignar números de teléfono](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="9fd6d-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


