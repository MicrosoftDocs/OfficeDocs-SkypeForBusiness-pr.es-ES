---
title: Configurar el uso de fotos de alta resolución en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Resumen: configure el uso de fotos de alta resolución en Exchange Server 2016 o Exchange Server 2013 y Skype empresarial Server.'
ms.openlocfilehash: 8d68cb75a053d7eb165383154514ca6ff8d1a941
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244328"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="d67bd-103">Configurar el uso de fotos de alta resolución en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d67bd-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="d67bd-104">**Resumen:** Configure el uso de fotos de alta resolución en Exchange Server 2016 o Exchange Server 2013 y Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d67bd-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="d67bd-105">En Skype empresarial Server, las fotos se pueden almacenar en un buzón de correo de usuario de Exchange Server 2016 o de Exchange Server 2013, lo que permite un tamaño de foto de hasta 648 píxeles por 648 píxeles.</span><span class="sxs-lookup"><span data-stu-id="d67bd-105">In Skype for Business Server photos can be stored in a user's Exchange Server 2016 or Exchange Server 2013 mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="d67bd-106">Además, Exchange Server puede cambiar automáticamente el tamaño de estas fotos para usarlas en diferentes productos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d67bd-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="d67bd-107">Normalmente, esto significa tres tamaños y resoluciones de foto diferentes:</span><span class="sxs-lookup"><span data-stu-id="d67bd-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="d67bd-108">64 píxeles por 64 píxeles, que es el tamaño usado por el atributo thumbnailPhoto de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d67bd-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="d67bd-109">Si carga una foto a Exchange Server, Exchange creará automáticamente un píxel de 64 por 64 píxel de la foto y actualizará el atributo thumbnailPhoto del usuario.</span><span class="sxs-lookup"><span data-stu-id="d67bd-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="d67bd-110">Sin embargo, ten en cuenta que el valor inverso no es verdadero: si actualizas manualmente el atributo thumbnailPhoto en Active Directory, no se actualizará automáticamente la foto en el buzón de Exchange del usuario.</span><span class="sxs-lookup"><span data-stu-id="d67bd-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="d67bd-111">96 píxeles por 96 píxeles, para su uso en Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, la aplicación Web de Skype empresarial y Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d67bd-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="d67bd-112">648 píxeles por 648 píxeles para usarlos en Skype empresarial y en la aplicación Web de Skype empresarial para Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d67bd-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d67bd-113">Si tiene los recursos, le recomendamos que cargue 648 x 648 fotos. que proporciona la resolución máxima y una calidad de imagen óptima en cualquiera de las aplicaciones de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="d67bd-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="d67bd-114">Cada foto JPEG con un tamaño de 648 x 648 y una profundidad de 24 bits da como resultado un tamaño de archivo de aproximadamente 240 kilobytes.</span><span class="sxs-lookup"><span data-stu-id="d67bd-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="d67bd-115">Eso significa que necesitará aproximadamente 1 megabyte de espacio en disco por cada 4 fotos de usuario.</span><span class="sxs-lookup"><span data-stu-id="d67bd-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="d67bd-116">Las fotos de alta resolución, a las que se accede mediante servicios web Exchange, se pueden cargar mediante usuarios que ejecuten Outlook 2013 Web App; los usuarios solo pueden actualizar su propia foto.</span><span class="sxs-lookup"><span data-stu-id="d67bd-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="d67bd-117">Los administradores, sin embargo, pueden actualizar la foto de cualquier usuario mediante el shell de administración de Exchange y una serie de comandos de Windows PowerShell similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d67bd-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="d67bd-118">El primer comando del ejemplo anterior usa el `Get-Content` cmdlet para leer el contenido del archivo C:\Photos\Kenmyer.jpg y almacenar los datos en una variable denominada $Photo.</span><span class="sxs-lookup"><span data-stu-id="d67bd-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="d67bd-119">En el segundo comando, se usa el `Set-UserPhoto` cmdlet de Exchange para cargar la foto y adjuntarla a la cuenta de usuario de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="d67bd-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d67bd-120">En este ejemplo, el nombre para mostrar de Active Directory de Ken Myer se usa como identidad de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="d67bd-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="d67bd-121">También puede hacer referencia a una cuenta de usuario usando otros identificadores, como la dirección SMTP del usuario o su nombre principal de usuario.</span><span class="sxs-lookup"><span data-stu-id="d67bd-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="d67bd-122">[https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) Para obtener más información, consulte la documentación del cmdlet Set-UserPhoto.</span><span class="sxs-lookup"><span data-stu-id="d67bd-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="d67bd-p107">Cargar la fotografía no equivale a asignarla a la cuenta de usuario de Ken Myer. Al cargar la fotografía, el resultado es que se muestra una vista previa de dicha fotografía en la página Opciones de Outlook Web App. Para asignar realmente la fotografía a la cuenta de usuario, haga clic en **Guardar** en la página Opciones o el administrador necesita ejecutar el tercer comando del ejemplo. Ese tercer comando usa el parámetro Save para asignar la fotografía a la cuenta de usuario de Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="d67bd-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="d67bd-127">Para comprobar que la nueva foto se ha asignado a la cuenta de usuario, Ken Myer puede iniciar sesión en Skype empresarial, seleccionar **Opciones**y, a continuación, seleccionar **mi foto**.</span><span class="sxs-lookup"><span data-stu-id="d67bd-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="d67bd-128">La foto recién cargada tiene que mostrarse como la foto personal de Ken.</span><span class="sxs-lookup"><span data-stu-id="d67bd-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="d67bd-129">Otra opción para comprobar la foto de cualquier usuario es que los administradores inicien Internet Explorer y naveguen a una dirección URL similar a esta:</span><span class="sxs-lookup"><span data-stu-id="d67bd-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

<span data-ttu-id="d67bd-130">Si el administrador puede ver la foto con Internet Explorer pero el usuario no puede ver su foto en Skype empresarial, es posible que haya un problema de conectividad con los servicios Web de Exchange o con el servicio Detección automática de Exchange.</span><span class="sxs-lookup"><span data-stu-id="d67bd-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="d67bd-131">Tenga en cuenta que no es necesario realizar ninguna configuración adicional para que esta foto esté disponible en Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d67bd-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="d67bd-132">En su lugar, la foto estará disponible al instante una vez que se haya cargado y el `Set-UserPhoto` cmdlet se haya ejecutado.</span><span class="sxs-lookup"><span data-stu-id="d67bd-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>
