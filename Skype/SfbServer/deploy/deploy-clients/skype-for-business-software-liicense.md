---
title: Skype de Skype salón del sistema de licencia de software de negocio
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lea este tema para obtener información acerca de cómo comprobar si tiene una licencia por volumen de software Skype Empresarial.
ms.openlocfilehash: e4ba03dacdce0056cb130299f551921042a6790d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207934"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Sistema de salas de Skype: licencia del software de Skype Empresarial
 
Lea este tema para obtener información acerca de cómo comprobar si tiene una licencia por volumen de software Skype Empresarial. 
  
Sistema de sala de Skype usa un Skype instalado para cliente de negocio, que requiere una licencia de volumen de software. Antes de implementar el primer sistema de sala de Skype, averiguar el estado de licencia por volumen de la implementación - mediante los servidores de administración de claves (KMS) o las claves de activación múltiple (MAK).
  
## <a name="key-management-servers-kms"></a>Servidores de administración de claves (KMS)

Si KMS se encuentran disponibles y distribuirá Skype para las activaciones de licencias por volumen de negocio, el sistema de sala de Skype se activará automáticamente el Skype para clientes empresariales. Para averiguar si está configurado el KMS realice lo siguiente:
  
Desde un símbolo del sistema, ejecute:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Para obtener más información, vea [cómo detectar hosts de KMS de Windows y de Office a través de DNS y quitar instancias no autorizadas](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Para configurar un KMS, vea [activación de KMS de Office 2013](https://technet.microsoft.com/library/ee624357.aspx) y [Gvlk para la activación de KMS y Active Directory de Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Clave de licencia de volumen Office 2013 genérico de Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (esta clave hace que el sistema de sala de Skype buscar un KMS en la red).
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Claves de activación múltiple (MAK) del Centro de servicios de licencias por volumen (VLSC)

Si el cliente usa cualquier otro software de licencia por volumen, el departamento de TI administrará las activaciones de software y el Contrato de licencias por volumen (VLA) con el VLSC. También Esto permitirá que la compañía compra de Skype para las activaciones de negocio VL, después de que la empresa puede obtener una clave de MAK para la entrada de la consola de administración del sistema de sala de Skype.
  
Un cliente con un VLA debe conocer sus credenciales de VLSC, que usará para administrar el contrato y obtener MAK. Si no sabe con seguridad, departamento de finanzas del cliente debe ser capaz de confirmar si el cliente ha pagado un VLA.
  
Para obtener una MAK, acceda al Centro de servicios de licencias por volumen para ver los contratos y descargar claves de producto (MAK). Para obtener más información, vaya al [Centro de servicio de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>MAK para Office 365 sin acceso al VLSC

Si el cliente no tiene un contrato de licencia por volumen, Skype para las activaciones de negocio será mucho más difícil de administrar. Sin embargo, los clientes de Office 365 sin acceso VLSC pueden obtener una MAK promocional proporcionando la siguiente información a los OEM vender el sistema de sala de Skype:
  
- Nombre de la compañía
    
- Nombre de contacto, correo electrónico y número de teléfono de la implementación
    
- Número de sistemas de implementada
    
- Fecha de implementación
    
- Si el cliente tiene un administrador de cuentas de técnicos de Microsoft, el TAM nombre e información de contacto
    

