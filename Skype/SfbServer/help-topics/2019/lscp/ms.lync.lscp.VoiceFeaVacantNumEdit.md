---
title: Número de teléfono sin asignar crear nuevos o editar los existentes
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.
ms.openlocfilehash: 43be74f40742428fd14aada2e2060ededb5c277a
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "22138598"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="a45ab-104">Número de teléfono sin asignar: Crear nuevos o editar los existentes</span><span class="sxs-lookup"><span data-stu-id="a45ab-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="a45ab-105">Mensajería unificada de Exchange sigue estando disponible en Skype para Business Server 2019 al integrar Skype para la empresa 2019 con Exchange 2013 o 2016 de Exchange.</span><span class="sxs-lookup"><span data-stu-id="a45ab-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="a45ab-106">Debido a los cambios en la compatibilidad en Exchange 2019, integración de mensajería unificada de Exchange se está desaprovisionamiento emphasised en favor de las características de correo de voz en la nube y operador automático de la nube.</span><span class="sxs-lookup"><span data-stu-id="a45ab-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasised in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  
 
<span data-ttu-id="a45ab-p103">Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="a45ab-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a45ab-109">Cuando haya terminado de crear un nuevo intervalo numérico sin asignar o modificar uno existente, haga clic en **Aceptar** para volver a la página **Número sin asignar** que se enumera todos los intervalos de números.</span><span class="sxs-lookup"><span data-stu-id="a45ab-109">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="a45ab-110">Los cambios realizados en la página **Nuevo Unassigned Number Range** o en la página **Editar Rage de número sin asignar** no se confirman en la base de datos hasta que haga clic en **Confirmar todo** en la página **Número sin asignar** .</span><span class="sxs-lookup"><span data-stu-id="a45ab-110">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="a45ab-111">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="a45ab-111">UI Reference</span></span>

<span data-ttu-id="a45ab-112">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="a45ab-112">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="a45ab-113">**Nombre** Escriba un nombre descriptivo que identifica el intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="a45ab-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="a45ab-114">Después de guardar el intervalo, no se puede cambiar este nombre.</span><span class="sxs-lookup"><span data-stu-id="a45ab-114">After you save the range, this name cannot be changed.</span></span>
    
- <span data-ttu-id="a45ab-115">**Intervalo de número** En el primer campo, escriba el número inicial del intervalo numérico sin asignar.</span><span class="sxs-lookup"><span data-stu-id="a45ab-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="a45ab-116">En el segundo campo, escriba el número final del rango.</span><span class="sxs-lookup"><span data-stu-id="a45ab-116">In the second field, type the ending number of the range.</span></span>
    
  - <span data-ttu-id="a45ab-117">El número inicial del intervalo debe ser menor o igual al número final.</span><span class="sxs-lookup"><span data-stu-id="a45ab-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
  - <span data-ttu-id="a45ab-118">Si el número inicial o final del intervalo incluye un número de extensión, ambos números del intervalo deben incluir la extensión y el número de extensión debe ser igual al número inicial y final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="a45ab-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
  - <span data-ttu-id="a45ab-119">El número debe coincidir con la expresión regular (tel:) ? (\+) ? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?.</span><span class="sxs-lookup"><span data-stu-id="a45ab-119">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="a45ab-120">Esto significa que el número de puede comenzar con la cadena tel: (si no se especifica esa cadena se agregará automáticamente para usted), un signo más (+) y un dígito del 1 al 9.</span><span class="sxs-lookup"><span data-stu-id="a45ab-120">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="a45ab-121">El número de teléfono puede tener hasta 17 dígitos y puede estar seguido de una extensión en formato ";ext=número de extensión".</span><span class="sxs-lookup"><span data-stu-id="a45ab-121">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
- <span data-ttu-id="a45ab-122">**Servicio de anuncio** Seleccione el **anuncio** para que la aplicación de anuncio controlar la llamada entrante o **Mensajería unificada de Exchange** para tener un operador de Exchange UM automático controlar la llamada entrante.</span><span class="sxs-lookup"><span data-stu-id="a45ab-122">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>
    
- <span data-ttu-id="a45ab-123">Si ha seleccionado **anuncio** para **el servicio de anuncio**:</span><span class="sxs-lookup"><span data-stu-id="a45ab-123">If you selected **Announcement** for **Announcement service**:</span></span>
    
  - <span data-ttu-id="a45ab-124">**FQDN del servidor de destino** Seleccione el identificador de servicio de la aplicación que se ejecuta la aplicación de anuncio que controlará las llamadas entrantes a este intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="a45ab-124">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>
    
  - <span data-ttu-id="a45ab-125">**Anuncio** Seleccione el anuncio se reproducirá para este intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="a45ab-125">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>
    
-  <span data-ttu-id="a45ab-126">Si ha seleccionado **Mensajería unificada de Exchange** para **el servicio de anuncio**:</span><span class="sxs-lookup"><span data-stu-id="a45ab-126">If you selected **Exchange UM** for **Announcement service**:</span></span>
    
  - <span data-ttu-id="a45ab-127">**Número de teléfono del operador automático** Seleccione el número de teléfono para el operador de Exchange UM automático.</span><span class="sxs-lookup"><span data-stu-id="a45ab-127">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>
    
<span data-ttu-id="a45ab-128">Para obtener información detallada sobre las capacidades y características de anuncio, consulte [Plan para la aplicación de anuncio en Skype para la empresa](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="a45ab-128">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="a45ab-129">Para obtener información detallada sobre cómo trabajar con intervalos numéricos sin asignar, vea [Configurar el enrutamiento de sin asignar números de teléfono](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="a45ab-129">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>
  

