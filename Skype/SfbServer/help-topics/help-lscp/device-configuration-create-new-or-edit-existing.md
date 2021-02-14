---
title: Configuración de dispositivo Crear nueva o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: En la página Nueva configuración de dispositivos o Editar configuración de dispositivos, puede crear o modificar una colección de configuraciones usadas para administrar Skype Empresarial Phone Edition. Estos valores le permiten configurar aspectos como el modo de seguridad requerido, el nivel de registro del dispositivo, los ajustes de calidad de servicio de voz (QoS) y especificar si el teléfono se bloquea automáticamente después de un periodo especificado de inactividad.
ms.openlocfilehash: ba84c6b9f820d0130940fce4dadad1cd38e7efec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807310"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="a414a-104">Configuración de dispositivo: Crear nuevos o editar los existentes</span><span class="sxs-lookup"><span data-stu-id="a414a-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="a414a-105">En la página  **Nueva configuración de dispositivos** o Editar configuración de dispositivos, puede crear o modificar una colección de configuraciones usadas para administrar Skype Empresarial Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="a414a-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="a414a-106">Estos valores le permiten configurar aspectos como el modo de seguridad requerido, el nivel de registro del dispositivo, los ajustes de calidad de servicio de voz (QoS) y especificar si el teléfono se bloquea automáticamente después de un periodo especificado de inactividad.</span><span class="sxs-lookup"><span data-stu-id="a414a-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="a414a-107">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="a414a-107">Tasks you can perform</span></span>

<span data-ttu-id="a414a-108">Puede realizar las siguientes tareas en la página **Nueva configuración de dispositivo** o **Editar configuración de dispositivo**:</span><span class="sxs-lookup"><span data-stu-id="a414a-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="a414a-109">Agregar una nueva configuración de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a414a-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="a414a-110">Modificar las propiedades de una configuración de dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="a414a-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="a414a-111">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="a414a-111">UI Reference</span></span>

<span data-ttu-id="a414a-112">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="a414a-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="a414a-113">**Ámbito** Identifica el ámbito (Global o Sitio) de la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a414a-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="a414a-114">**Nombre** Puedes agregar o modificar el nombre de la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a414a-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="a414a-115">**Seguridad SIP** Puede configurar los requisitos de transporte y autenticación para dispositivos Skype Empresarial Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="a414a-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="a414a-116">Puede seleccionar entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a414a-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="a414a-117">**Bajo** Permitir cualquier tipo de autorización o transporte.</span><span class="sxs-lookup"><span data-stu-id="a414a-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="a414a-118">**Medio** Se requiere NTLM o Kerberos para la autenticación de usuario.</span><span class="sxs-lookup"><span data-stu-id="a414a-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="a414a-119">**Alto** Se requiere NTLM o Kerberos para la autenticación de usuario y TLS para las conexiones SIP.</span><span class="sxs-lookup"><span data-stu-id="a414a-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="a414a-120">**Nivel de registro** Puedes habilitar el registro en el dispositivo uc.</span><span class="sxs-lookup"><span data-stu-id="a414a-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="a414a-121">Los valores válidos son: Off; Low; Medium; and High.</span><span class="sxs-lookup"><span data-stu-id="a414a-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="a414a-122">El valor predeterminado es Off.</span><span class="sxs-lookup"><span data-stu-id="a414a-122">The default value is Off.</span></span>
    
- <span data-ttu-id="a414a-123">**Calidad de servicio de voz (QoS)** Puede especificar el valor DSCP asignado al tráfico de voz que procede de un dispositivo Skype Empresarial Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="a414a-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="a414a-124">El valor predeterminado es 40.</span><span class="sxs-lookup"><span data-stu-id="a414a-124">The default is 40.</span></span> <span data-ttu-id="a414a-125">No obstante, 40 no es el valor usado normalmente para el tráfico de audio; en su lugar, el tráfico de audio se marca casi siempre con el código 46 de DSCP.</span><span class="sxs-lookup"><span data-stu-id="a414a-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="a414a-126">Para mantener la coherencia en la red, debe cambiar este valor a 46.</span><span class="sxs-lookup"><span data-stu-id="a414a-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="a414a-127">**Bloqueo del teléfono** Puede especificar si los teléfonos UC se bloquearán automáticamente después de un período especificado de inactividad.</span><span class="sxs-lookup"><span data-stu-id="a414a-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="a414a-128">A continuación se incluyen los valores que puede configurar:</span><span class="sxs-lookup"><span data-stu-id="a414a-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="a414a-129">**Exigir el bloqueo del dispositivo** Puedes aplicar el bloqueo del dispositivo si seleccionas esta casilla.</span><span class="sxs-lookup"><span data-stu-id="a414a-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="a414a-130">**Longitud mínima del PIN** Puede especificar la longitud mínima del número de identificación personal (PIN) que se usa para desbloquear el teléfono.</span><span class="sxs-lookup"><span data-stu-id="a414a-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="a414a-131">La longitud del PIN puede oscilar entre cuatro y 15 dígitos.</span><span class="sxs-lookup"><span data-stu-id="a414a-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="a414a-132">La longitud predeterminada es de seis dígitos.</span><span class="sxs-lookup"><span data-stu-id="a414a-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="a414a-133">**Tiempo de espera de bloqueo del teléfono** Puede especificar el período mínimo de tiempo antes de que el teléfono se bloquee.</span><span class="sxs-lookup"><span data-stu-id="a414a-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="a414a-134">El intervalo para el tiempo de espera va de 0 a 60 minutos; el valor predeterminado es de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="a414a-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="a414a-135">Especifique el valor en el formato HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="a414a-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a414a-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="a414a-136">See also</span></span>

[<span data-ttu-id="a414a-137">Configuración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="a414a-137">Device Configuration</span></span>](device-configuration.md)

[<span data-ttu-id="a414a-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="a414a-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
