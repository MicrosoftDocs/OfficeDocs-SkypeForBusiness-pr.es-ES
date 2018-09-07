---
title: ¿Cuántos números de teléfono puede conseguir?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 61dfb27c-5bfa-4481-a930-9c026e73ff3a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Al obtener números de teléfono para su organización, puede obtener más números de teléfono que los que le corresponden por las licencias que tiene asignadas. Sin embargo, esto depende de los tipos de números de teléfono y del tipo de licencias que ha adquirido y asignado. Puede hacer clic en distintos tipos de números de teléfono utilizados para llamar a los planes para obtener información acerca de los números de teléfono diferentes que se usan en Skype para profesionales en línea.
ms.openlocfilehash: a0d4e1273a49ac4f9e82cb98c8baddf22772f9d4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856310"
---
# <a name="how-many-phone-numbers-can-you-get"></a>¿Cuántos números de teléfono puede conseguir?

Al obtener números de teléfono para su organización, puede obtener más números de teléfono que los que le corresponden por las licencias que tiene asignadas. Sin embargo, esto depende de los tipos de números de teléfono y del tipo de licencias que ha adquirido y asignado. Puede hacer clic en [distintos tipos de números de teléfono utilizados para llamar a los planes](different-kinds-of-phone-numbers-used-for-calling-plans.md) para obtener información acerca de los números de teléfono diferentes que se usan en Skype para profesionales en línea.
  
Puede ver el número de los números de teléfono que puede obtener en la página de **números de teléfono** en el Skype para el centro de administración de negocio, o bien puede ejecutar el cmdlet [Get-CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/library/mt634605.aspx) .
  
> [!IMPORTANT]
> Los siguientes límites no incluyen números de teléfono en los que haya realizado portabilidad o que haya transferido a Microsoft. 
  
## <a name="how-many-phone-numbers-you-can-get"></a>¿Cuántos números de teléfono puede obtener?

||||
|:-----|:-----|:-----|
|**Este es el tipo de número de teléfono** <br/> |**¿Cómo se obtiene el total de números de teléfono?** <br/> |**Este es un ejemplo** <br/> |
|Número de usuario (suscriptor)  <br/> |El número de números de teléfono es igual que el número total de licencias de **Llamar a planear nacional** o **nacionales y llamar a planear internacional** multiplicado por 1.1 + 10 otros números de teléfono. <br/> |Si dispone de 50 usuarios en total con puede ser un nacional al llamar a planear y nacionales y llamar a planear internacional, puede adquirir de número de teléfono de **65** **(50 x 1.1 + 10)**. <br/> |
|Número de servicio de pago  <br/> | El número de números de teléfono es igual al número total de licencias de **Sistema telefónico** y **Conferencias de Audio** y usa las siguientes: <br/>  Si hay **1-25 licencias**, se proporcionan **5** números de teléfono. <br/>  Si hay **26-49 licencias**, se proporcionan **10** números de teléfono. <br/>  Si no hay **licencias de 50-99** se conceden los números de teléfono de **20** . <br/>  Si hay **100-149 licencias**, se proporcionan **30** números de teléfono. <br/>  Si hay **150-199 licencias**, se proporcionan **40** números de teléfono. <br/>  Si hay **200-499 licencias**, se proporcionan **65** números de teléfono. <br/>  Si hay **500-749 licencias**, se proporcionan **90** números de teléfono. <br/>  Si hay **750-999 licencias**, se proporcionan **110** números de teléfono. <br/>  Si hay **1.000-1.249 licencias**, se proporcionan **125** números de teléfono. <br/>  Si no hay **licencias de 1.250-1,499** se conceden **135** los números de teléfono. <br/>  Si hay **1.500-1.999 licencias**, se proporcionan **160** números de teléfono. <br/>  Si hay **2.000-2.999 licencias**, se proporcionan **210** números de teléfono. <br/>  Si hay **3.000-6.999 licencias**, se proporcionan **420** números de teléfono. <br/>  Si hay **7.000-9.999 licencias**, se proporcionan **500** números de teléfono. <br/>  Si hay **10.000-14.999 licencias**, se proporcionan **600** números de teléfono. <br/>  Si hay **15.000-19.999 licencias**, se proporcionan **700** números de teléfono. <br/>  Si hay **20.000-49.999 licencias**, se proporcionan **1000** números de teléfono. <br/>  Si hay **más de 50.000**, se proporcionan **1.500** números de teléfono. <br/> |Si tiene un total de **51** **Sistema telefónico** y licencias de **Conferencias de Audio** , puede obtener los números de servicio de pago de **20** . <br/> |
|Número de servicio gratuito  <br/> | El número de números de teléfono es igual al número total de licencias de **Sistema telefónico** y **Conferencias de Audio** y usa las siguientes: <br/>  Si hay **1-25 licencias**, se proporcionan **5** números de teléfono. <br/>  Si hay **26-49 licencias**, se proporcionan **10** números de teléfono. <br/>  Si no hay **licencias de 50-99** se conceden los números de teléfono de **20** . <br/>  Si hay **100-149 licencias**, se proporcionan **30** números de teléfono. <br/>  Si hay **150-199 licencias**, se proporcionan **40** números de teléfono. <br/>  Si hay **200-499 licencias**, se proporcionan **65** números de teléfono. <br/>  Si hay **500-749 licencias**, se proporcionan **90** números de teléfono. <br/>  Si hay **750-999 licencias**, se proporcionan **110** números de teléfono. <br/>  Si hay **1.000-1.249 licencias**, se proporcionan **125** números de teléfono. <br/>  Si no hay **licencias de 1.250-1,499** se conceden **135** los números de teléfono. <br/>  Si hay **1.500-1.999 licencias**, se proporcionan **160** números de teléfono. <br/>  Si hay **2.000-2.999 licencias**, se proporcionan **210** números de teléfono. <br/>  Si hay **3.000-6.999 licencias**, se proporcionan **420** números de teléfono. <br/>  Si hay **7.000-9.999 licencias**, se proporcionan **500** números de teléfono. <br/>  Si hay **10.000-14.999 licencias**, se proporcionan **600** números de teléfono. <br/>  Si hay **15.000-19.999 licencias**, se proporcionan **700** números de teléfono. <br/>  Si hay **20.000-49.999 licencias**, se proporcionan **1000** números de teléfono. <br/>  Si hay **más de 50.000**, se proporcionan **1.500** números de teléfono. <br/> |Si tiene un total de **1001** **Sistema telefónico** y licencias de **Conferencias de Audio** , puede obtener los números de un servicio gratuito de **125** . <br/> <br/> **Importante:** [Facturación de créditos Communications](set-up-communications-credits-for-your-organization.md) es necesario para reservar y use los números de teléfono gratuito.          |
   
> [!NOTE]
> Si necesita obtener más números de teléfono, [póngase en contacto con el soporte de productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
  
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 