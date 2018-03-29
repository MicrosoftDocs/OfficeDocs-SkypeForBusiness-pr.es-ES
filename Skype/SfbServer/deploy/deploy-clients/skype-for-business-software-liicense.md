---
title: Skype de Skype sala sistema de licencia de software de negocios
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lea este tema para obtener información acerca de cómo comprobar si tiene una licencia por volumen de software Skype Empresarial.
ms.openlocfilehash: e91a009c29647031d91e791ba5fd41ccc4578d1e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Sistema de salas de Skype: licencia del software de Skype Empresarial
 
Lea este tema para obtener información acerca de cómo comprobar si tiene una licencia por volumen de software Skype Empresarial. 
  
Sistema de sala de Skype utiliza un Skype instalado para cliente de negocio, que requiere una licencia de volumen de software. Antes de implementar el primer sistema de sala de Skype, averigüe el estado de la licencia de volumen de la implementación - mediante servidores de administración de claves (KMS) o claves de activación múltiple (MAK).
  
## <a name="key-management-servers-kms"></a>Servidores de administración de claves (KMS)

Si KMS están vigentes y distribuirá Skype para las activaciones de licencia de volumen de negocio, el sistema de sala de Skype se activará automáticamente el Skype para cliente de empresa. Para averiguar si está configurado el KMS realice lo siguiente:
  
Desde un símbolo del sistema, ejecute:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Para obtener más información, vea [cómo descubrir hosts de KMS de Windows y de Office mediante DNS y eliminar instancias no autorizadas](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Para configurar un KMS, consulte [activación de KMS de Office 2013](https://technet.microsoft.com/en-us/library/ee624357.aspx) y [GVLKs para la activación de KMS y Active Directory de Office 2013](https://technet.microsoft.com/en-us/library/dn385360.aspx)
  
Clave de licencia de volumen Office 2013 genérico para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (esta clave hace que el sistema de sala de Skype para que busque un KMS en la red).
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Claves de activación múltiple (MAK) del Centro de servicios de licencias por volumen (VLSC)

Si el cliente usa cualquier otro software de licencia por volumen, el departamento de TI administrará las activaciones de software y el Contrato de licencias por volumen (VLA) con el VLSC. Esto también permitirá a la empresa adquirir Skype para activaciones de negocio VL, después de que la empresa puede obtener una MAK para la entrada de la consola de administración del sistema de sala de Skype.
  
Un cliente con un VLA debe conocer sus credenciales de VLSC, que usará para administrar el contrato y obtener MAK. Si no está seguro, departamento de finanzas del cliente debe ser capaz de confirmar si el cliente ha pagado por un VLA.
  
Para obtener una MAK, acceda al Centro de servicios de licencias por volumen para ver los contratos y descargar claves de producto (MAK). Para obtener más información, vaya al [Centro de servicio de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>MAK para Office 365 sin acceso al VLSC

Si el cliente no tiene un contrato de licencia de volumen, Skype para las activaciones de negocio será mucho más difícil de administrar. Sin embargo, Office 365 sin acceso VLSC pueden obtener los clientes una MAK promocional proporcionando la siguiente información al OEM vendiendo el sistema de sala de Skype:
  
- Nombre de la compañía
    
- Nombre de contacto, correo electrónico y número de teléfono de la implementación
    
- Número de sistemas implementados
    
- Fecha de implementación
    
- Si el cliente tiene Microsoft administrador técnico de cuentas, el TAM nombre e información de contacto
    

