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
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: b774c368674f421c11f36339ef7188ea8de82e64
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865164"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurar la red para Difusión de reunión de Skype

Después de [habilitar Difusión de reunión de](enable-skype-meeting-broadcast.md) Skype, debe configurar su red. Realice este paso si quiere realizar seminarios web y otras difusiones para personas que no forme parte de su empresa.

> [!IMPORTANT]
> Skype Empresarial Online se retirará el 31 de julio de 2021, momento en el que finalizará el acceso al servicio. Animamos a los clientes a comenzar la actualización a Microsoft Teams, el cliente principal de comunicaciones y trabajo en equipo en Microsoft 365.

Si no tiene experiencia con la configuración del firewall, analice contratar un [socio de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para que lleve a cabo este paso por usted.

Para omitir este paso y, en su lugar, agregar otra empresa a su federación para poder invitarlos a difusiones, siga los pasos de Permitir que los usuarios se contacten con usuarios externos de [Skype Empresarial.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

## <a name="step-1-set-up-allowed-domains"></a>Paso 1: Configurar dominios permitidos

Use **uno** de los siguientes métodos para configurar dominios permitidos:

## #

 **Método 1: Usar el centro de administración**

1. Vaya al centro de administración y, a continuación, en la barra de navegación izquierda, haga clic en Complementos de Servicios de configuración y, a continuación, elija  >  **&amp;** **Skype Empresarial.**

2. En la **página Uso compartido** externo, en Excepciones de dominio, seleccione Todos los dominios están **bloqueados** excepto **y** escriba los siguientes dominios separados con una coma (,):

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Haga clic en **Guardar**.

## #

 **Método 2: Usar Windows PowerShell**

- En el **menú Inicio, haga** clic con el **botón derecho Windows PowerShell** haga clic en Ejecutar **como administrador.** In the **Windows PowerShell** window, type each line and press Enter.

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Paso 2: Agregar dominios, direcciones URL y direcciones IP de Difusión de reunión de Skype

El segundo paso del proceso de configuración consiste en agregar primero los dominios necesarios y después agregar las direcciones IP y las URL necesarias para que funcione la Difusión de reunión de Skype.

- **Agregue las direcciones IP** [](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)y URL de puntos de conexión de Skype Empresarial Online necesarias.

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurar Difusión de reunión de Skype en organizaciones e implementaciones híbridas

Si tiene una organización de Skype Empresarial Online y una implementación local de Lync Server 2010, Microsoft Lync Server 2013 y Skype Empresarial Server 2015, y tiene usuarios tanto en línea como local, hay otros pasos de configuración que deberá realizar además de los anteriores para permitir que su organización local se comunique con Skype Empresarial Online y permita que todos los usuarios se unan a una Difusión de reunión de Skype. Para ver cuáles son esos requisitos, consulte [Configurar la implementación local para la Difusión de reunión de Skype](https://go.microsoft.com/fwlink/?LinkId=617070).

## <a name="related-topics"></a>Temas relacionados

[Habilitar la Difusión de reunión de Skype](enable-skype-meeting-broadcast.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



