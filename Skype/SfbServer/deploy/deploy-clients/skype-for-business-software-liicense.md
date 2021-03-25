---
title: Licencia de software de Skype Room System Skype Empresarial
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lea este tema para obtener información sobre cómo comprobar si tiene una licencia por volumen de software de Skype Empresarial.
ms.openlocfilehash: 40b72e39fc0edc23b4cc0d17f82ba633c2ac24af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113096"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Sistema de salón de Skype: licencia de software de Skype Empresarial
 
Lea este tema para obtener información sobre cómo comprobar si tiene una licencia por volumen de software de Skype Empresarial. 
  
Skype Room System usa un cliente de Skype Empresarial instalado, que requiere una licencia por volumen de software. Antes de implementar el primer sistema de sala de Skype, descubra el estado de la licencia por volumen de la implementación: mediante los servidores de administración de claves (KMS) o las claves de activación múltiple (MAK).
  
## <a name="key-management-servers-kms"></a>Servidores de administración de claves (KMS)

Si el KMS está en su lugar y distribuirá las activaciones de licencias por volumen de Skype Empresarial, el sistema de sala de Skype activará automáticamente el cliente de Skype Empresarial. Para averiguar si kms están en su lugar:
  
Desde un símbolo del sistema, ejecute:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Para obtener más información, [vea How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Para configurar un KMS, vea Activación de KMS de [Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) y GVLKs para KMS y activación de [Active Directory de Office 2013](/DeployOffice/vlactivation/gvlks)
  
Clave de licencia por volumen genérica de Office 2013 para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Esta clave hace que el sistema de sala de Skype busque un KMS en la red).
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Claves de activación múltiples (MAK) del Centro de servicio de licencias por volumen (VLSC)

Si el cliente usa cualquier otro software de licencia por volumen, el departamento de TI administrará las activaciones de software y el Contrato de licencia por volumen (VLA) mediante vlsc. Esto también permitirá a la compañía comprar activaciones DE VIP de Skype Empresarial, después de lo cual la compañía puede obtener una MAK para la entrada en la Consola de administración del sistema de salón de Skype.
  
Un cliente con un VLA debe conocer sus credenciales VLSC, que se usarán para administrar el contrato y obtener MAK. Si no se tiene certeza, el departamento de finanzas del cliente debe poder confirmar si el cliente ha pagado por una VLA.
  
Para obtener una MAK, acceda al Centro de servicios de licencias por volumen para ver acuerdos y descargar claves de producto (MAK). Para obtener más información, vaya al [Centro de servicios de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK para Microsoft 365 u Office 365 sin acceso a VLSC

Si el cliente no tiene un contrato de licencia por volumen, las activaciones de Skype Empresarial serán mucho más difíciles de administrar. Sin embargo, los clientes de Microsoft 365 y Office 365 sin acceso a VLSC pueden obtener una MAK promocional proporcionando la siguiente información al OEM que vende el sistema de salón de Skype:
  
- Nombre de la compañía
    
- Nombre de contacto de implementación, correo electrónico y número de teléfono
    
- Número de sistemas implementados
    
- Fecha de implementación
    
- Si el cliente tiene un Administrador de cuentas técnico de Microsoft, el nombre y la información de contacto del TAM
