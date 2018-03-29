---
title: Configuración de dispositivo crear nuevo o editar existente
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: En la página Configuración de dispositivo nuevo o editar la configuración del dispositivo, puede crear o modificar una colección de valores utilizados para administrar Skype para Business Phone Edition. Estos valores permiten configurar aspectos como el modo de seguridad necesario, el nivel de registro del dispositivo, los ajustes de calidad de servicio de voz (QoS) y, asimismo, especificar si el teléfono se bloquea automáticamente después de un periodo de inactividad específico.
ms.openlocfilehash: c6d8f291b6602ad41ca2942e2d4b507d2727bcd1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="0c955-104">Configuración de dispositivo: Crear nueva o editar existente</span><span class="sxs-lookup"><span data-stu-id="0c955-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="0c955-105">En la página **Configuración de dispositivo nuevo** o **Editar la configuración del dispositivo** , puede crear o modificar una colección de valores utilizados para administrar Skype para Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="0c955-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="0c955-106">Estos valores permiten configurar aspectos como el modo de seguridad necesario, el nivel de registro del dispositivo, los ajustes de calidad de servicio de voz (QoS) y, asimismo, especificar si el teléfono se bloquea automáticamente después de un periodo de inactividad específico.</span><span class="sxs-lookup"><span data-stu-id="0c955-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="0c955-107">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="0c955-107">Tasks you can perform</span></span>

<span data-ttu-id="0c955-108">En las páginas **Nueva configuración de dispositivo** o **Editar configuración de dispositivo** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="0c955-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="0c955-109">Agregar una nueva configuración de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0c955-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="0c955-110">Modificar las propiedades de una configuración de dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="0c955-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="0c955-111">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="0c955-111">UI Reference</span></span>

<span data-ttu-id="0c955-112">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="0c955-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="0c955-113">**Ámbito de aplicación** Identifica el ámbito (Global o sitio) de la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0c955-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="0c955-114">**Nombre** Puede agregar o modificar el nombre de la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0c955-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="0c955-115">**Seguridad de SIP** Puede configurar los requisitos de autenticación y transporte para Skype para dispositivos Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="0c955-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="0c955-116">Puede seleccionar entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="0c955-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="0c955-117">**Bajo** Permitir a cualquier tipo de autorización o de transporte.</span><span class="sxs-lookup"><span data-stu-id="0c955-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="0c955-118">**Medio** Es necesario para la autenticación de usuario NTLM o Kerberos.</span><span class="sxs-lookup"><span data-stu-id="0c955-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="0c955-119">**Alta** Se requiere autenticación de usuario NTLM o Kerberos y se requiere TLS para las conexiones SIP.</span><span class="sxs-lookup"><span data-stu-id="0c955-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="0c955-120">**Nivel de registro** Puede habilitar el registro en el dispositivo de comunicaciones unificadas.</span><span class="sxs-lookup"><span data-stu-id="0c955-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="0c955-121">Los valores válidos son: Desactivado, Bajo, Medio y Alto.</span><span class="sxs-lookup"><span data-stu-id="0c955-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="0c955-122">El valor predeterminado es Desactivado.</span><span class="sxs-lookup"><span data-stu-id="0c955-122">The default value is Off.</span></span>
    
- <span data-ttu-id="0c955-123">**Voz de calidad de servicio (QoS)** Puede especificar el valor DSCP asignado al tráfico de voz que emana de un Skype para dispositivo Business Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="0c955-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="0c955-124">El valor predeterminado es 40.</span><span class="sxs-lookup"><span data-stu-id="0c955-124">The default is 40.</span></span> <span data-ttu-id="0c955-125">Pero, 40 no es el valor usado normalmente para el tráfico de audio; en su lugar, el tráfico de audio se marca casi siempre con el código 46 de DSCP.</span><span class="sxs-lookup"><span data-stu-id="0c955-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="0c955-126">Para mantener la coherencia en la red, necesita cambiar este valor a 46.</span><span class="sxs-lookup"><span data-stu-id="0c955-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="0c955-127">**Bloqueo del teléfono** Puede especificar si se permite o no UC teléfonos bloquearán automáticamente a sí mismos después de un período especificado de inactividad.</span><span class="sxs-lookup"><span data-stu-id="0c955-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="0c955-128">A continuación se incluyen los valores que puede configurar:</span><span class="sxs-lookup"><span data-stu-id="0c955-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="0c955-129">**Exigir el bloqueo de dispositivo** Puede exigir el dispositivo de bloqueo activando esta casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="0c955-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="0c955-130">**Longitud de PIN mínimo** Puede especificar la longitud mínima para el número de identificación personal (PIN) que se utiliza para desbloquear el teléfono.</span><span class="sxs-lookup"><span data-stu-id="0c955-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="0c955-131">La longitud del PIN puede oscilar entre cuatro y 15 dígitos.</span><span class="sxs-lookup"><span data-stu-id="0c955-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="0c955-132">La longitud predeterminada es de seis dígitos.</span><span class="sxs-lookup"><span data-stu-id="0c955-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="0c955-133">**Tiempo de espera de bloqueo de teléfono** Puede especificar la longitud mínima de tiempo antes de los bloqueos de teléfono propio.</span><span class="sxs-lookup"><span data-stu-id="0c955-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="0c955-134">El intervalo para el tiempo de espera va de 0 a 60 minutos; el valor predeterminado es de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="0c955-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="0c955-135">Especifique el valor con el formato HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="0c955-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0c955-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c955-136">See also</span></span>

#### 

[<span data-ttu-id="0c955-137">Configuración del dispositivo</span><span class="sxs-lookup"><span data-stu-id="0c955-137">Device Configuration</span></span>](device-configuration.md)
#### 

[<span data-ttu-id="0c955-138">Conjunto de CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="0c955-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)

