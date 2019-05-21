---
title: Proceso de implementación para la aplicación de anuncios en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Proceso de implementación y pasos para la aplicación de anuncios en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 77d15c4ce749a97ec11ed5d5e083ccf6fa2aecfa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275611"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="80da2-103">Proceso de implementación para la aplicación de anuncios en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="80da2-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="80da2-104">Proceso de implementación y pasos para la aplicación de anuncios en Skype empresarial Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="80da2-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="80da2-105">La aplicación de anuncios es una característica de voz empresarial que le permite configurar lo que sucede con las llamadas a extensiones no asignadas (extensiones que son válidas para su organización, pero que no están asignadas a una persona o teléfono).</span><span class="sxs-lookup"><span data-stu-id="80da2-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="80da2-106">Por ejemplo, puede configurar las llamadas a números sin asignar para que se reproduzca un mensaje, se transfieran a otro destino o ambas cosas.</span><span class="sxs-lookup"><span data-stu-id="80da2-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="80da2-107">La aplicación de anuncios se instala como una característica de la aplicación de grupo de respuesta en el servidor front-end o el servidor Standard Edition al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="80da2-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="80da2-108">Tiene que configurar Anuncios mediante la carga de los archivos de audio o la configuración de texto a voz (TTS) y la tabla de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="80da2-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="80da2-109">Esta sección proporciona una descripción general de los pasos necesarios para implementar la aplicación de anuncios.</span><span class="sxs-lookup"><span data-stu-id="80da2-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="80da2-110">Debe implementar la telefonía IP empresarial antes de configurar los anuncios.</span><span class="sxs-lookup"><span data-stu-id="80da2-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="80da2-111">Los componentes requeridos por la aplicación de anuncios se instalan y se habilitan al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="80da2-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="80da2-112">**Proceso de implementación de anuncios**</span><span class="sxs-lookup"><span data-stu-id="80da2-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="80da2-113">**Fase**</span><span class="sxs-lookup"><span data-stu-id="80da2-113">**Phase**</span></span>|<span data-ttu-id="80da2-114">**Pasos**</span><span class="sxs-lookup"><span data-stu-id="80da2-114">**Steps**</span></span>|<span data-ttu-id="80da2-115">**Roles**</span><span class="sxs-lookup"><span data-stu-id="80da2-115">**Roles**</span></span>|<span data-ttu-id="80da2-116">**Documentación de implementación**</span><span class="sxs-lookup"><span data-stu-id="80da2-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="80da2-117">Configurar opciones de anuncio</span><span class="sxs-lookup"><span data-stu-id="80da2-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="80da2-118">Cree el anuncio grabando y cargando archivos de audio, o bien usando texto a voz (TTS).</span><span class="sxs-lookup"><span data-stu-id="80da2-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="80da2-119">Configure los intervalos de números no asignados de la tabla de números no asignados y asócielos al anuncio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="80da2-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="80da2-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="80da2-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="80da2-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="80da2-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="80da2-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="80da2-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="80da2-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="80da2-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="80da2-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="80da2-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="80da2-125">Crear o eliminar un anuncio en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="80da2-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="80da2-126">Crear o modificar un intervalo de números sin asignar en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="80da2-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="80da2-127">Comprobar la implementación de anuncios</span><span class="sxs-lookup"><span data-stu-id="80da2-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="80da2-128">Escuche los anuncios para comprobar que la configuración funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="80da2-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="80da2-129">Faculta Comprobar la implementación de la presentación en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="80da2-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

