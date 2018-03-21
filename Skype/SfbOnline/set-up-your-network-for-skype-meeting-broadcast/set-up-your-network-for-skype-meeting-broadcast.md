---
title: "Configurar la red para Difusión de reunión de Skype"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.date: 01/22/2018
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: 9dab3a7e74b9f69a3df6bd06c3ad868d109343fe
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurar la red para Difusión de reunión de Skype

Después de [Habilitar la difusión de reunión Skype](enable-skype-meeting-broadcast.md) difusión de reunión Skype, debe configurar la red. Realice este paso si desea celebrar seminarios y otras difusiones para personas fuera de su negocio.
  
Si no tiene experiencia con la configuración del firewall, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.
  
Para omitir este paso y en su lugar agregar otra empresa para la federación para invitarlos a las difusiones, siga los pasos de [Permitir a los usuarios ponerse en contacto con Skype externo para usuarios empresariales](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).
  
## <a name="step-1-set-up-allowed-domains"></a>Paso 1: Configurar dominios permitidos

Utilice **uno** de los métodos siguientes para configurar dominios permitidos:
  
### 

 **Método 1: Utilizar el centro de administración de Office 365**
  
1. Ir al **Centro de administración de Office 365** y, a continuación, haga clic en **configuración**en la barra de navegación izquierda, > **servicios &amp; complementos**y, a continuación, elija **Skype para el negocio**.
    
2. En la página **Compartir externo** en **excepciones de dominio**, seleccione **todos los dominios están bloqueados excepto**y escriba los siguientes dominios separados con una coma (,):
    
  - noammeetings.Lync.com
    
  - emeameetings.Lync.com
    
  - apacmeetings.Lync.com
    
  - Resources.Lync.com
    
3. Haga clic en **Guardar**.
    
### 

 **Método 2: Usar Windows PowerShell**
  
- En el **Menú Inicio**, haga clic en **Windows PowerShell** y haga clic en **Ejecutar como administrador**. In the **Windows PowerShell** window, type each line and press Enter.
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Paso 2: Agregar Skype reunión difusión dominios, direcciones URL e IP direcciones

El segundo paso en el proceso de instalación es agregar primero los dominios que son necesarios y, a continuación, agregar las direcciones IP y las direcciones URL que son necesarias para la difusión de reunión Skype trabajar.
  
- **Agregar el Skype necesario para los negocios en línea de direcciones URL de extremo y se requieren direcciones IP viendo cuáles** [aquí](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).
    
## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurar Difusión de reunión de Skype en organizaciones e implementaciones híbridas

Si tiene un Skype para una implementación local de Lync Server 2010, Microsoft Lync Server 2013 y Skype y organización empresarial en línea para Business Server 2015 y tiene tanto los usuarios en línea y local, existen otros pasos de configuración que se debe hacer en Además de las anteriores permiten a su organización local para comunicarse con Skype para los negocios en línea y permitir que todos los usuarios puedan crear y unirse a una reunión de Skype difusión. Para ver cuáles son esos requisitos, consulte [Configurar la implementación local para la Difusión de reunión de Skype](https://go.microsoft.com/fwlink/?LinkId=617070).
  
## <a name="related-topics"></a>See also

[Habilitar Difusión de reunión de Skype](enable-skype-meeting-broadcast.md)
  
[URL de Office 365 e intervalos de direcciones IP](http://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

