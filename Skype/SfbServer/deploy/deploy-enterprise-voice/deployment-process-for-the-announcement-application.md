---
title: Proceso de implementación de la aplicación Anuncio en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Proceso de implementación y pasos para la aplicación Anuncio en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812310"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="53372-103">Proceso de implementación de la aplicación Anuncio en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="53372-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="53372-104">Proceso de implementación y pasos para la aplicación Anuncio en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="53372-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="53372-105">La aplicación Anuncio es una característica de Telefonía IP empresarial que permite configurar lo que sucede con las llamadas a extensiones sin asignar (extensiones que son válidas para su organización, pero que no están asignadas a una persona o un teléfono).</span><span class="sxs-lookup"><span data-stu-id="53372-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="53372-106">Por ejemplo, puede configurar las llamadas a números sin asignar para que se reproduzca un mensaje, se transfieran a otro destino o ambas cosas.</span><span class="sxs-lookup"><span data-stu-id="53372-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="53372-107">La aplicación Anuncio se instala como una característica de la aplicación Grupo de respuesta en el servidor front-end o en el servidor Standard Edition al implementar Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="53372-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="53372-108">Tiene que configurar Anuncios mediante la carga de los archivos de audio o la configuración de texto a voz (TTS) y la tabla de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="53372-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="53372-109">En esta sección se proporciona información general sobre los pasos necesarios para implementar la aplicación Anuncio.</span><span class="sxs-lookup"><span data-stu-id="53372-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="53372-110">Debe implementar los Telefonía IP empresarial antes de configurar los anuncios.</span><span class="sxs-lookup"><span data-stu-id="53372-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="53372-111">Los componentes requeridos por la aplicación Anuncio se instalan y habilitan al implementar Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="53372-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="53372-112">**Proceso de implementación de anuncios**</span><span class="sxs-lookup"><span data-stu-id="53372-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="53372-113">**Fase**</span><span class="sxs-lookup"><span data-stu-id="53372-113">**Phase**</span></span>|<span data-ttu-id="53372-114">**Pasos**</span><span class="sxs-lookup"><span data-stu-id="53372-114">**Steps**</span></span>|<span data-ttu-id="53372-115">**Roles**</span><span class="sxs-lookup"><span data-stu-id="53372-115">**Roles**</span></span>|<span data-ttu-id="53372-116">**Documentación de implementación**</span><span class="sxs-lookup"><span data-stu-id="53372-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="53372-117">Configurar opciones de anuncio</span><span class="sxs-lookup"><span data-stu-id="53372-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="53372-118">Cree el anuncio grabando y cargando archivos de audio, o bien usando texto a voz (TTS).</span><span class="sxs-lookup"><span data-stu-id="53372-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="53372-119">Configure los intervalos de números no asignados de la tabla de números no asignados y asócielos al anuncio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="53372-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="53372-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="53372-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="53372-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="53372-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="53372-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="53372-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="53372-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="53372-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="53372-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="53372-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="53372-125">Crear o eliminar un anuncio en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="53372-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="53372-126">Crear o modificar un intervalo de números sin signo en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="53372-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="53372-127">Comprobar la implementación de anuncios</span><span class="sxs-lookup"><span data-stu-id="53372-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="53372-128">Escuche los anuncios para comprobar que la configuración funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="53372-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="53372-129">(Opcional) Comprobar la implementación de anuncios en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="53372-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

