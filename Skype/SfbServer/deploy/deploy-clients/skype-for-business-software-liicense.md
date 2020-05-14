---
title: Licencia de software de Skype empresarial para sistemas de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lea este tema para obtener información sobre cómo comprobar si tiene una licencia por volumen de software de Skype empresarial.
ms.openlocfilehash: a44e95d8cd488e2b12e03ee9848ef3d1b254180c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220930"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Sistema de salas de Skype: licencia del software de Skype empresarial
 
Lea este tema para obtener información sobre cómo comprobar si tiene una licencia por volumen de software de Skype empresarial. 
  
El sistema de salas de Skype usa un cliente de Skype empresarial instalado, que requiere una licencia por volumen de software. Antes de implementar el primer sistema de salas de Skype, descubra el estado de la licencia por volumen de la implementación: mediante el uso de servidores de administración de claves (KMS) o claves de activación múltiple (MAK).
  
## <a name="key-management-servers-kms"></a>Servidores de administración de claves (KMS)

Si KMS está en marcha y va a distribuir las activaciones de licencias por volumen de Skype empresarial, el sistema de salas de Skype activará automáticamente el cliente de Skype empresarial. Para averiguar si KMS está en su ubicación:
  
Desde un símbolo del sistema, ejecute:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Para obtener más información, vea [Cómo detectar hosts de kms de Office y Windows a través de DNS y eliminar instancias no autorizadas](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Para configurar un KMS, consulte la [activación de kms de office 2013](https://technet.microsoft.com/library/ee624357.aspx) y [GVLK para la activación de kms y active directory de Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Clave de licencia por volumen genérica de Office 2013 para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (esta clave hace que el sistema de salas de Skype busque un KMS en la red).
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Claves de activación múltiple (MAK) del centro de servicios de licencias por volumen (VLSC)

Si el cliente usa cualquier otro software de licencia por volumen, el Departamento de ti administrará las activaciones de software y el contrato de licencia por volumen (VLA) con el VLSC. Esto también permitirá a la empresa comprar activaciones VL de Skype empresarial, después de lo cual la empresa puede obtener una MAK para la entrada en la consola de administración del sistema de salas de Skype.
  
Un cliente con una VLA debe conocer sus credenciales de VLSC, que se usarán para administrar el contrato y obtener MAK. Si no está seguro, el Departamento de finanzas del cliente debe poder confirmar si el cliente ha pagado por un VLA.
  
Para obtener una MAK, obtenga acceso al centro de servicios de licencias por volumen para ver contratos y descargar claves de producto (MAK). Para obtener más información, vaya al [centro de servicios de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK para Microsoft 365 o Office 365 sin acceso a VLSC

Si el cliente no tiene un contrato de licencia por volumen, las activaciones de Skype empresarial serán mucho más difíciles de administrar. Sin embargo, los clientes de Microsoft 365 y Office 365 que no tienen acceso a VLSC pueden obtener una MAK de promoción proporcionando la siguiente información al OEM vendiendo el sistema de salas de Skype:
  
- Nombre de la organización
    
- Nombre de contacto, correo electrónico y número de teléfono de la implementación
    
- Número de sistemas implementados
    
- Fecha de implementación
    
- Si el cliente tiene un administrador de cuentas técnico de Microsoft, el nombre y la información de contacto del TAM
    

