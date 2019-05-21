---
title: Licencia del software de Skype empresarial para sistemas de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lea este tema para obtener información acerca de cómo comprobar si tiene una licencia por volumen de software Skype Empresarial.
ms.openlocfilehash: d1d04dc6c80d4e7e04b6ed7a946dfc393a308933
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287688"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Sistema de salas de Skype: licencia del software de Skype Empresarial
 
Lea este tema para obtener información acerca de cómo comprobar si tiene una licencia por volumen de software Skype Empresarial. 
  
El sistema de salas de Skype usa un cliente de Skype para empresas instalado, que requiere una licencia por volumen de software. Antes de implementar el primer sistema de la sala de Skype, averigüe el estado de la licencia por volumen de la implementación: con los servidores de administración de claves (KMS) o las claves de activación múltiple (MAK).
  
## <a name="key-management-servers-kms"></a>Servidores de administración de claves (KMS)

Si KMS está en el lugar y va a distribuir las activaciones de licencias por volumen de Skype empresarial, el sistema de salas de Skype activará automáticamente el cliente de Skype empresarial. Para averiguar si está configurado el KMS realice lo siguiente:
  
Desde un símbolo del sistema, ejecute:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Para obtener más información, consulte [Cómo descubrir los hosts de kms de Office y Windows a través de DNS y quitar instancias no autorizadas](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Para configurar un KMS, consulte [activación de kms de office 2013](https://technet.microsoft.com/library/ee624357.aspx) y [GVLKs para kms y activación de active directory de Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Clave de licencia por volumen genérica de Office 2013 para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (esta clave hace que el sistema de la sala de Skype busque un KMS en la red).
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Claves de activación múltiple (MAK) del Centro de servicios de licencias por volumen (VLSC)

Si el cliente usa cualquier otro software de licencia por volumen, el departamento de TI administrará las activaciones de software y el Contrato de licencias por volumen (VLA) con el VLSC. Esto también permitirá a la empresa comprar activaciones VL de Skype empresarial, después de las cuales la empresa puede obtener una MAK para la entrada en la consola de administración de sistemas de salas de Skype.
  
Un cliente con un VLA debe conocer sus credenciales de VLSC, que usará para administrar el contrato y obtener MAK. Si no está seguro, el Departamento de finanzas del cliente debe poder confirmar si el cliente ha recibido un VLA.
  
Para obtener una MAK, acceda al Centro de servicios de licencias por volumen para ver los contratos y descargar claves de producto (MAK). Para obtener más información, vaya al [centro de servicios de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>MAK para Office 365 sin acceso al VLSC

Si el cliente no tiene un contrato de licencia por volumen, las activaciones de Skype para empresas serán mucho más difíciles de administrar. Sin embargo, los clientes de Office 365 sin acceso VLSC pueden obtener una MAK de promoción proporcionando la siguiente información al OEM vendiendo el sistema de salas de Skype:
  
- Nombre de la compañía
    
- Nombre de contacto, correo electrónico y número de teléfono de la implementación
    
- Número de sistemas implementados
    
- Fecha de implementación
    
- Si el cliente tiene un administrador de cuentas técnico de Microsoft, el nombre y la información de contacto del TAM
    

