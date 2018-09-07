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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: e1f10ad5036e2866cc480491e98bd2dd7396895a
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23862219"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurar la red para Difusión de reunión de Skype

Después de [Habilitar la difusión de reunión de Skype](enable-skype-meeting-broadcast.md) Difundir presentación de reunión de Skype, debe configurar la red. Realice este paso si desea que se espera seminarios Web y otras difusiones para las personas de fuera de su negocio.

Si no tiene experiencia con la configuración del firewall, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.

Para omitir este paso y en su lugar agregar otra empresa para la federación, por lo que puede invitarlos a las difusiones, siga los pasos de [Permitir a los usuarios ponerse en contacto con Skype externo para los usuarios empresariales](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).

## <a name="step-1-set-up-allowed-domains"></a>Paso 1: Configurar los dominios permitidos

Utilice **uno** de los métodos siguientes para configurar los dominios permitidos:

###

 **Método 1: Usar el centro de administración de Office 365**

1. Vaya al **Centro de administración de Office 365** y, a continuación, en el panel de navegación izquierdo, haga clic en **configuración de** > **servicios &amp; complementos**y, a continuación, elija **Skype para la empresa**.

2. En la página de **uso compartido externo** , en **excepciones de dominio**, seleccione **todos los dominios están bloqueados, excepto**y especifique los siguientes dominios separados con una coma (,):

  - noammeetings.Lync.com

  - emeameetings.Lync.com

  - apacmeetings.Lync.com

  - Resources.Lync.com

3. Haga clic en **Guardar**.

###

 **Método 2: Uso de Windows PowerShell**

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Paso 2: Agregar reunión Difundir presentación de Skype dominios, las direcciones URL, IP y direcciones

El segundo paso en el proceso de instalación es para que usted agregar dominios que son necesarios y, a continuación, agregue las direcciones IP y las direcciones URL que son necesarias para la difusión de reunión de Skype trabajar.

- **Agregar el Skype necesaria para direcciones URL de extremo en línea de negocio y las direcciones IP viendo cuáles son necesarias** [aquí](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurar Difusión de reunión de Skype en organizaciones e implementaciones híbridas

Si tiene un Skype para la organización en línea de negocio y una implementación local de Lync Server 2010, Microsoft Lync Server 2013 y Skype para Business Server 2015 y tienen los usuarios tanto en línea y local, hay otros pasos de configuración que debe llevar a cabo en Además de las anteriores para habilitar la organización local para comunicarse con Skype para profesionales en línea y permitir que todos los usuarios puedan crear y unirse a una reunión de Skype Difundir presentación. Para ver cuáles son esos requisitos, consulte [Configurar la implementación local para la Difusión de reunión de Skype](https://go.microsoft.com/fwlink/?LinkId=617070).

## <a name="related-topics"></a>Temas relacionados

[Habilitar Difusión de reunión de Skype](enable-skype-meeting-broadcast.md)

[URL de Office 365 e intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



