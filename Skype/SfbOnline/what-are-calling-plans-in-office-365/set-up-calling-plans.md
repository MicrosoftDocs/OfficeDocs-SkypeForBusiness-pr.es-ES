---
title: Configurar las llamadas RTC en Skype Empresarial
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 03/30/2018
ms.topic: article
ms.assetid: 57893158-1acd-44ac-acaf-19f58264a9e0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
- LIL_Placement
description: 'Learn how in Office 365 Calling Plan (PSTN Calling plan) to buy and set up licenses, get phone numbers, add and assign emergency locations and phone numbers to users, and tell your users about their new phone numbers. '
ms.openlocfilehash: dcba074f1c0e6966ef0632a95035e681aa25a194
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="set-up-calling-plans"></a>Configurar las llamadas RTC en Skype Empresarial

Calls to other Skype for Business users are free, but if you want your users to be able to call phones outside of your business, get a Domestic Calling Plan or an International Calling Plan in Office 365. It's easy to set this up for your business. 

## <a name="step-1-find-out-if-calling-plans-are-available-in-your-countryregion"></a>Paso 1: Averiguar si llamar a planes están disponibles en su país o región

Vaya a [disponibilidad de país y región para conferencias de Audio y planes de llamada](..//country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) y seleccione su país o región para obtener la información de disponibilidad acerca de planes de llamada, así como información acerca de las llamadas de conferencia de Audio, sistema de teléfono y número gratuito números y créditos de comunicaciones.
  
## <a name="step-2-buy-and-assign-licenses"></a>Paso 2: Comprar y asignar licencias

1. If the Phone System in Office 365 feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses. Una vez haya licencias del **Sistema de teléfono** , compra [Llamar a planes de Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md). See [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), and buy the licenses and plan. 
    
    > [!TIP]
    > Las licencias de PBX en la nube y los planes de llamadas de voz van de la mano. Por ello, para ver la opción para comprar un plan de llamadas de voz, primero debe tener las licencias de PBX en la nube.
  
2. First assign the licenses, and then assign a Calling Plan to the people in your organization. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
## <a name="step-3-get-phone-numbers"></a>Paso 3: Obtener números de teléfono

Hay tres maneras de obtener nuevos números de usuario:

- **Utilice el Skype para el centro de administración de negocios.** Para algunos países o regiones, puede obtener los números de los puentes de conferencia usando el Skype para el centro de administración de negocios, vea [números de teléfono del servicio de obtención](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Los números existentes de puerto.** Puede trasladar o transferir números existentes desde su actual proveedor de servicios o la compañía de teléfono para Office 365. Consulte [transferir números de teléfono a Office 365](transfer-phone-numbers-to-office-365.md) o [administrar números de teléfono de la organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para obtener más información para ayudarle a hacerlo.  
  
- **Utilizar un formulario de solicitud para nuevos números.** A veces (dependiendo de su país o región) no podrá obtener sus números de teléfono de nuevo usando el Skype para el centro de administración de negocios o necesita determinados números de teléfono o códigos de área. En ese caso, tendrá que descargar un formulario y enviárnoslo. Para obtener más información, vea [administrar números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) . 


## <a name="step-4-add-emergency-addresses-and-locations-for-your-organization"></a>Paso 4: Agregue direcciones de emergencia y ubicaciones para su organización
<a name="bkmk_add_addresses"> </a>

Una dirección de emergencia debe estar asociada con un número de teléfono; Cuando sucede esta asociación puede variar entre los países y regiones. Por ejemplo, en los Estados Unidos, debe asociar una dirección de emergencia cuando se asigna el número de teléfono al usuario. En el Reino Unido, debe asociar una dirección al número de teléfono de emergencia al obtener los números de teléfono de Office 365 o transferir números de teléfono de su proveedor de servicio actual. 

Para agregar una dirección de emergencia para su organización, en el Skype para el centro de administración de negocios vaya a **voz** > **ubicaciones de emergencia** > **Agregar nueva dirección**. Para obtener más información, vea [Add o remove y dirección de emergencia para su organización](../what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization.md) .

Para agregar una ubicación de emergencia para su organización en el Skype para el centro de administración de negocios, vaya a **voz** > **ubicaciones de emergencia** > **Agregar nueva dirección**. Para obtener información detallada, vea [Agregar, cambiar o quitar una ubicación de emergencia para su organización](../what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization.md) .

    
## <a name="step-5-assign-an-emergency-address-and-a-phone-number-to-a-user"></a>Paso 5: Asignar una dirección de emergencia y un número de teléfono a un usuario
<a name="bkmk_add_addresses"> </a>

Cuando configura una llamada a planes de Office 365, debe asignar un número de teléfono y dirección de emergencia a cada uno de los usuarios. Debe crear la dirección de emergencia antes de asociarlo con un número de teléfono. 

Para agregar una dirección de emergencia para un usuario en el Skype para el centro de administración de negocios, vaya a **voz** > **usuarios de voz** > **ubicación de emergencia** > **Asignar número** > **Cambiar ubicación**. Para obtener más información, vea [asignar o cambiar una dirección de emergencia para un usuario](../what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user.md) .

   > [!NOTE]
   > También puede asignar una dirección de emergencia cuando se asigna un número de teléfono.

Para asignar un número de teléfono a un usuario en el Skype para el centro de administración de negocios, vaya a **voz** > **usuarios de voz** > **Asignar número** > **Cambiar ubicación**. Para obtener más información, vea [asignar, cambiar o quitar un número de teléfono de un usuario](../what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user.md) .

    
## <a name="step-6-tell-your-users-about-their-new-phone-numbers"></a>Paso 6: Indique a los usuarios acerca de sus nuevos números de teléfono
<a name="bkmk_add_addresses"> </a>

Recomendamos enviar correo o usar el método de comunicación preferido de su empresa para informar a sus miembros los nuevos números de teléfono. 

Le mostramos cómo pueden ver ese número de teléfono en su aplicación de **Skype para empresas** :
  
1. Inicie sesión en Skype Empresarial en el escritorio.
    
2. Elija **Configuración** > **Herramientas** > **Opciones**. 
    
     ![To view your phone number, go to Settings > Tools > Options.](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. A continuación, elija **Teléfonos**. 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
En los **Equipos de Microsoft**, los usuarios pueden ver su número de teléfono haciendo clic en **llamadas** en la exploración de la izquierda. El número de teléfono se muestra encima del teclado.

![Un usuario puede ver su número de Teams de Microsoft haciendo clic en llamadas en la exploración de la izquierda.](../images/teams-phone-number.png)

## <a name="what-else-do-you-need-to-know"></a>¿Qué más necesita saber?
<a name="bkmk_add_addresses"> </a>

- Con frecuencia, la dirección de emergencia también se conoce como dirección civil, dirección postal o dirección física. Es la dirección postal o civil del domicilio social de su organización.
    
- Las ubicaciones de emergencia no se validan, solo se validan las direcciones de emergencia.
    
- Si quiere más información sobre las direcciones de emergencia, vea [¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?](../what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing.md)
    
## <a name="do-you-want-to-automate-assigning-phone-numbers"></a>¿Quiere automatizar la asignación de números de teléfono?
<a name="bkmk_add_addresses"> </a>

Si tiene experiencia con Windows PowerShell, puede usar los siguientes cmdlets para automatizar la asignación de números de teléfono a sus usuarios. 
  
- [Get-CsOnlineTelephoneNumber](https://technet.microsoft.com/en-us/library/mt243818.aspx): recupera los números de teléfono del Directorio de voz empresarial.
    
- [Set-CsOnlineVoiceUser](https://technet.microsoft.com/en-us/library/mt243817.aspx): configura los números de teléfono.
    
Para obtener más información, consulte [Referencia rápida:Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://technet.microsoft.com/en-us/library/dn362776%28v=ocs.15%29.aspx).
  
   > [!NOTE]
   > Si necesita obtener más números de teléfono, [póngase en contacto con el soporte de productos para empresas: ayuda para administradores](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 