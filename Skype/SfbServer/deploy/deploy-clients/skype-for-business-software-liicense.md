---
title: Skype room system Skype Empresarial de software
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lea este tema para obtener información sobre cómo comprobar si tiene una Skype Empresarial de software por volumen.
ms.openlocfilehash: 0e8fcc9b4dc9dec481af7b0a1d976d590c40def0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399994"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype room system: Skype Empresarial de software
 
Lea este tema para obtener información sobre cómo comprobar si tiene una Skype Empresarial de software por volumen. 
  
Skype Room System usa un cliente de Skype Empresarial instalado, que requiere una licencia por volumen de software. Antes de implementar el primer sistema de sala de Skype, descubra el estado de licencia por volumen de la implementación: mediante los servidores de administración de claves (KMS) o varias claves de activación (MAK).
  
## <a name="key-management-servers-kms"></a>Servidores de administración de claves (KMS)

Si KMS y distribuirá activaciones de licencia por volumen Skype Empresarial, el sistema de sala de Skype activará automáticamente el Skype Empresarial cliente. Para averiguar si KMS están en su lugar:
  
Desde un símbolo del sistema, ejecute:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Para configurar un KMS, consulte KMS [activation of Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) and [GVLKs for KMS and Active Directory activation of Office 2013](/DeployOffice/vlactivation/gvlks)
  
Office clave de licencia por volumen genérica de 2013 para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Esta clave hace que el sistema de sala de Skype busque un KMS en la red).
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Claves de activación múltiples (MAK) del Centro de servicio de licencias por volumen (VLSC)

Si el cliente usa cualquier otro software de licencia por volumen, el departamento de TI administrará las activaciones de software y el Contrato de licencia por volumen (VLA) mediante vlsc. Esto también permitirá a la compañía comprar activaciones Skype Empresarial VL, después de lo cual la compañía puede obtener una MAK para la entrada en la consola de administración del sistema de sala Skype de sala.
  
Un cliente con un VLA debe conocer sus credenciales VLSC, que se usarán para administrar el contrato y obtener MAK. Si no se tiene certeza, el departamento de finanzas del cliente debe poder confirmar si el cliente ha pagado por una VLA.
  
Para obtener una MAK, acceda al Centro de servicios de licencias por volumen para ver acuerdos y descargar claves de producto (MAK). Para obtener más información, vaya al [Centro de servicios de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK para Microsoft 365 o Office 365 sin acceso VLSC

Si el cliente no tiene un contrato de licencia por volumen, Skype Empresarial las activaciones serán mucho más difíciles de administrar. Sin embargo, Microsoft 365 y Office 365 sin acceso a VLSC pueden obtener una MAK promocional proporcionando la siguiente información al OEM que vende el Skype room system:
  
- Nombre de la compañía
    
- Nombre de contacto de implementación, correo electrónico y número de teléfono
    
- Número de sistemas implementados
    
- Fecha de implementación
    
- Si el cliente tiene un Administrador de cuentas técnico de Microsoft, el nombre y la información de contacto del TAM
