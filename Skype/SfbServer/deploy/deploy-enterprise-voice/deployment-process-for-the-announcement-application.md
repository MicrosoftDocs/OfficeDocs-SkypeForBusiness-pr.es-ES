---
title: Proceso de implementación de la aplicación de anuncio en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Proceso de implementación y los pasos para la aplicación de anuncio en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 5adaea25903968935cbaa00639546926781c004c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23888074"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="7bfbe-103">Proceso de implementación de la aplicación de anuncio en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7bfbe-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="7bfbe-104">Proceso de implementación y los pasos para la aplicación de anuncio en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7bfbe-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="7bfbe-105">La aplicación de anuncio es una característica de Enterprise Voice que le permite configurar lo que ocurre con las llamadas a extensiones sin asignar (extensiones que son válidas para su organización, pero no están asignadas a una persona o un teléfono).</span><span class="sxs-lookup"><span data-stu-id="7bfbe-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="7bfbe-106">Por ejemplo, puede configurar las llamadas a números sin asignar para que se reproduzca un mensaje, se transfieran a otro destino o ambas cosas.</span><span class="sxs-lookup"><span data-stu-id="7bfbe-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="7bfbe-107">La aplicación de anuncio se instala como una característica de aplicación de grupo de respuesta en el servidor Front-End o Standard Edition al implementar Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7bfbe-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="7bfbe-108">Tiene que configurar Anuncios mediante la carga de los archivos de audio o la configuración de texto a voz (TTS) y la tabla de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="7bfbe-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="7bfbe-109">En esta sección se proporciona una visión general de los pasos necesarios para implementar la aplicación de anuncio.</span><span class="sxs-lookup"><span data-stu-id="7bfbe-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="7bfbe-110">Debe implementar Enterprise Voice antes de configurar anuncios.</span><span class="sxs-lookup"><span data-stu-id="7bfbe-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="7bfbe-111">Los componentes requeridos por la aplicación de anuncio están instalados y habilitados al implementar Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7bfbe-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="7bfbe-112">**Proceso de implementación de anuncios**</span><span class="sxs-lookup"><span data-stu-id="7bfbe-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="7bfbe-113">**Fase**</span><span class="sxs-lookup"><span data-stu-id="7bfbe-113">**Phase**</span></span>|<span data-ttu-id="7bfbe-114">**Pasos**</span><span class="sxs-lookup"><span data-stu-id="7bfbe-114">**Steps**</span></span>|<span data-ttu-id="7bfbe-115">**Roles**</span><span class="sxs-lookup"><span data-stu-id="7bfbe-115">**Roles**</span></span>|<span data-ttu-id="7bfbe-116">**Documentación de implementación**</span><span class="sxs-lookup"><span data-stu-id="7bfbe-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7bfbe-117">Configurar opciones de anuncio</span><span class="sxs-lookup"><span data-stu-id="7bfbe-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="7bfbe-118">Cree el anuncio grabando y cargando archivos de audio, o bien usando texto a voz (TTS).</span><span class="sxs-lookup"><span data-stu-id="7bfbe-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="7bfbe-119">Configure los intervalos de números no asignados de la tabla de números no asignados y asócielos al anuncio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7bfbe-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="7bfbe-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7bfbe-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="7bfbe-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="7bfbe-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="7bfbe-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="7bfbe-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="7bfbe-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7bfbe-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="7bfbe-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="7bfbe-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="7bfbe-125">Crear o eliminar un anuncio en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7bfbe-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="7bfbe-126">Crear o modificar un intervalo de números sin asignar en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7bfbe-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="7bfbe-127">Comprobar la implementación de anuncios</span><span class="sxs-lookup"><span data-stu-id="7bfbe-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="7bfbe-128">Escuche los anuncios para comprobar que la configuración funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="7bfbe-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="7bfbe-129">(Opcional) Comprobación de la implementación de anuncio en Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="7bfbe-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

