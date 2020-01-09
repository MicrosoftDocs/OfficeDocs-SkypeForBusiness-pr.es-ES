---
title: Configurar la red para Difusión de reunión de Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: 95ad00be416a53e6e861ce4e9f235bded8e8075a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990985"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurar la red para Difusión de reunión de Skype

Después de [Habilitar](enable-skype-meeting-broadcast.md) la difusión de reunión de Skype de difusión de reunión de Skype, debe configurar su red. Lleve a cabo este paso si desea mantener seminarios y otras difusiones para personas fuera de su empresa.

Si no tiene experiencia con la configuración del firewall, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.

Para omitir este paso y, en su lugar, agregar otra empresa a su Federación para poder invitarlos a las difusiones, siga los pasos que se indican en [permitir que los usuarios se pongan en contacto con usuarios externos de Skype empresarial](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).

## <a name="step-1-set-up-allowed-domains"></a>Paso 1: configurar los dominios permitidos

Use **uno** de los métodos siguientes para configurar los dominios permitidos:

## #

 **Método 1: usar el centro de administración**

1. Vaya al centro de administración y, a continuación, en el explorador de navegación izquierdo, haga clic en**Complementos de servicios &amp; **de **configuración** > y, a continuación, elija **Skype empresarial**.

2. En la página **uso compartido externo** , en **excepciones de dominio**, seleccione **todos los dominios están bloqueados excepto**e introduzca los siguientes dominios separados por comas (,):

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Haga clic en **Guardar**.

## #

 **Método 2: usar Windows PowerShell**

- En el **menú Inicio**, haga clic con el botón derecho en **Windows PowerShell** y haga clic en **Ejecutar como administrador**. In the **Windows PowerShell** window, type each line and press Enter.

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Paso 2: agregar dominios de difusión de reunión de Skype, direcciones URL y direcciones IP

El segundo paso del proceso de configuración es agregar primero los dominios necesarios y, a continuación, agregar direcciones IP y direcciones URL necesarias para que la difusión de reunión de Skype funcione.

- **Agregue las direcciones IP y las direcciones URL de los puntos de conexión de Skype empresarial online que se** necesitan [aquí](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurar Difusión de reunión de Skype en organizaciones e implementaciones híbridas

Si dispone de una organización de Skype empresarial online y una implementación local de Lync Server 2010, Microsoft Lync Server 2013 y Skype empresarial Server 2015, y tiene usuarios en línea y locales, hay otros pasos de configuración que necesitará realizar en complemento de los anteriores para permitir que su organización local se comunique con Skype empresarial online y permitir que todos los usuarios se unan a una difusión de reunión de Skype. Para ver cuáles son esos requisitos, consulte [Configurar la implementación local para la Difusión de reunión de Skype](https://go.microsoft.com/fwlink/?LinkId=617070).

## <a name="related-topics"></a>Temas relacionados

[Habilitar la Difusión de reunión de Skype](enable-skype-meeting-broadcast.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



