---
title: ¿Cuántos números de teléfono puede obtener?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.assetid: 61dfb27c-5bfa-4481-a930-9c026e73ff3a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.quantity
- seo-marvel-mar2020
description: Obtenga información sobre cuántos números de teléfono puede obtener en Microsoft Teams en función del tipo de número y la cantidad de licencias que tiene.
ms.openlocfilehash: b8c6c8a2e1fa2b1b882a4fc2ddbbb5e904e5f6f7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141113"
---
# <a name="how-many-phone-numbers-can-you-get"></a>¿Cuántos números de teléfono puede obtener?

Al obtener números de teléfono para su organización, puede obtener más números de teléfono que los que le corresponden por las licencias que tiene asignadas. Sin embargo, esto depende de los tipos de números de teléfono y del tipo de licencias que ha adquirido y asignado. Puede hacer clic [en Distintos tipos de](different-kinds-of-phone-numbers-used-for-calling-plans.md) números de teléfono usados para los planes de llamadas para conocer los distintos números de teléfono que se usan en Microsoft Teams.
  
Puede ver la cantidad de números de  teléfono que puede obtener en la página Obtener números de teléfono en el Centro de administración de Microsoft Teams o puede ejecutar el cmdlet [Get-CsOnlineTelephoneNumberAvailableCount.](https://technet.microsoft.com/library/mt634605.aspx)
  
> [!IMPORTANT]
> Los siguientes límites no incluyen números de teléfono en los que haya realizado portabilidad o que haya transferido a Microsoft. 
  
## <a name="how-many-phone-numbers-you-can-get"></a>¿Cuántos números de teléfono puede obtener?

||||
|:-----|:-----|:-----|
|**Este es el tipo de número de teléfono** <br/> |**¿Cómo se obtiene el total de números de teléfono?** <br/> |**Este es un ejemplo** <br/> |
|Número de usuario (suscriptor)  <br/> |La cantidad de números de teléfono es igual al número total de licencias de **plan** de llamadas nacionales o de **planes** de llamadas nacionales e internacionales multiplicado por 1,1 + 10 números de teléfono adicionales. <br/> |Si tengo 50 usuarios en total con un plan de llamadas nacionales o un plan de llamadas nacionales e internacionales, puede adquirir **65** números de teléfono **(50 x 1,1 + 10).** <br/> |
|Número de servicio de pago  <br/> | La cantidad de números de teléfono  es igual al número total de licencias de Sistema telefónico y **Audioconferencia** y usa lo siguiente: <br/>  Si hay **1-25 licencias**, se proporcionan **5** números de teléfono. <br/>  Si hay **26-49 licencias**, se proporcionan **10** números de teléfono. <br/>  Si hay **entre 50 y 99** licencias, se **darán 20** números de teléfono. <br/>  Si hay **100-149 licencias**, se proporcionan **30** números de teléfono. <br/>  Si hay **150-199 licencias**, se proporcionan **40** números de teléfono. <br/>  Si hay **200-499 licencias**, se proporcionan **65** números de teléfono. <br/>  Si hay **500-749 licencias**, se proporcionan **90** números de teléfono. <br/>  Si hay **750-999 licencias**, se proporcionan **110** números de teléfono. <br/>  Si hay **1.000-1.249 licencias**, se proporcionan **125** números de teléfono. <br/>  Si hay **1.250-1.499** licencias, se **darán 135** números de teléfono. <br/>  Si hay **1.500-1.999 licencias**, se proporcionan **160** números de teléfono. <br/>  Si hay **2.000-2.999 licencias**, se proporcionan **210** números de teléfono. <br/>  Si hay **3.000-6.999 licencias**, se proporcionan **420** números de teléfono. <br/>  Si hay **7.000-9.999 licencias**, se proporcionan **500** números de teléfono. <br/>  Si hay **10.000-14.999 licencias**, se proporcionan **600** números de teléfono. <br/>  Si hay **15.000-19.999 licencias**, se proporcionan **700** números de teléfono. <br/>  Si hay **20.000-49.999 licencias**, se proporcionan **1000** números de teléfono. <br/>  Si hay **más de 50.000**, se proporcionan **1.500** números de teléfono. <br/> |Si tiene un total de **51**  licencias de Sistema telefónico y **Audioconferencia,** puede obtener **20 números** de servicio de pago. <br/> |
|Número de servicio gratuito  <br/> | La cantidad de números de teléfono  es igual al número total de licencias de Sistema telefónico y **Audioconferencia** y usa lo siguiente: <br/>  Si hay **1-25 licencias**, se proporcionan **5** números de teléfono. <br/>  Si hay **26-49 licencias**, se proporcionan **10** números de teléfono. <br/>  Si hay **entre 50 y 99** licencias, se **darán 20** números de teléfono. <br/>  Si hay **100-149 licencias**, se proporcionan **30** números de teléfono. <br/>  Si hay **150-199 licencias**, se proporcionan **40** números de teléfono. <br/>  Si hay **200-499 licencias**, se proporcionan **65** números de teléfono. <br/>  Si hay **500-749 licencias**, se proporcionan **90** números de teléfono. <br/>  Si hay **750-999 licencias**, se proporcionan **110** números de teléfono. <br/>  Si hay **1.000-1.249 licencias**, se proporcionan **125** números de teléfono. <br/>  Si hay **1.250-1.499** licencias, se **darán 135** números de teléfono. <br/>  Si hay **1.500-1.999 licencias**, se proporcionan **160** números de teléfono. <br/>  Si hay **2.000-2.999 licencias**, se proporcionan **210** números de teléfono. <br/>  Si hay **3.000-6.999 licencias**, se proporcionan **420** números de teléfono. <br/>  Si hay **7.000-9.999 licencias**, se proporcionan **500** números de teléfono. <br/>  Si hay **10.000-14.999 licencias**, se proporcionan **600** números de teléfono. <br/>  Si hay **15.000-19.999 licencias**, se proporcionan **700** números de teléfono. <br/>  Si hay **20.000-49.999 licencias**, se proporcionan **1000** números de teléfono. <br/>  Si hay **más de 50.000**, se proporcionan **1.500** números de teléfono. <br/> |Si tiene un total de **1001**  licencias de Sistema telefónico y **Audioconferencia,** puede obtener **125** números de servicio gratuitos. <br/> <br/> **Importante: se requiere** [la facturación](set-up-communications-credits-for-your-organization.md) de créditos de comunicaciones para reservar y usar números de teléfono gratuitos.          |
   
> [!NOTE]
> Si necesita obtener más números de teléfono, [póngase en contacto con el soporte de productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
  
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)

[Etiqueta de declinación de responsabilidades en llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 