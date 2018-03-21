---
title: Configurar las llamadas RTC en Skype Empresarial
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
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
ms.openlocfilehash: 871edfa997e9267213480a448eda952a7927783b
ms.sourcegitcommit: 6c59400d2e677c1022f320c91cd7f102b99d292b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2018
---
# <a name="set-up-calling-plans"></a>Configurar las llamadas RTC en Skype Empresarial

Calls to other Skype for Business users are free, but if you want your users to be able to call phones outside of your business, get a Domestic Calling Plan or an International Calling Plan in Office 365. It's easy to set this up for your business. 
  
## <a name="step-1-buy-and-assign-licenses"></a>Paso 1: Comprar licencias y asignarlas

1. If the Phone System in Office 365 feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses. Una vez haya licencias del **Sistema de teléfono** , compra [Llamar a planes de Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md). See [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), and buy the licenses and plan. 
    
    > [!TIP]
    > Las licencias de PBX en la nube y los planes de llamadas de voz van de la mano. Por ello, para ver la opción para comprar un plan de llamadas de voz, primero debe tener las licencias de PBX en la nube.
  
2. First assign the licenses, and then assign a Calling Plan to the people in your organization. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
## <a name="step-2-get-phone-numbers"></a>Paso 2: Obtener números de teléfono

El orden de los pasos es levemente diferente si se encuentra fuera de los Estados Unidos. Esto se debe a que en algunos países o regiones, puede obtener una dirección de emergencia con el número de teléfono que recibe de Office 365 o el que usted transfiere. Por ello, si está fuera de los Estados Unidos, lleve a cabo primero el [Paso 3: Agregar direcciones y ubicaciones de emergencia para la organización](set-up-calling-plans.md#bkmk_add_addresses) y, a continuación, realice el **Paso 2:Obtener los números de teléfono**.
  
1. SI está usando números de teléfono de Office 365, siga estos pasos. **Si necesita transferir los números de teléfono existentes desde otro proveedor de servicios, siga los pasos en [Transferir números de teléfono a Skype Empresarial Online](transfer-phone-numbers-to-office-365.md)**.
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype Empresarial >** **Voz**.

    > [!IMPORTANT] 
    > Para que poder ver la opción de **voz** en la exploración de la izquierda en el Skype para el centro de administración de negocios, primero debe comprar una licencia adicional para **Conferencias de Audio** , una licencia del módulo de **Sistema de teléfono** o al menos una **licencia Enterprise E5**.
   
4. Choose **Phone numbers**. You'll see how many **Phone System** licenses you have, to give you an idea how many phone numbers to request.
    
    > [!TIP]
    > Puede adquirir varios números de teléfono, sin importar que tenga una cantidad menor de licencias. Para determinar cuántos números de teléfono pueden adquirirse, agregue el 10 % de las licencias y después 10 más. Por ejemplo, si adquirió 100 licencias, puede adquirir 120 números de teléfono. Consulte [cuántos números puedo conseguir?](how-many-phone-numbers-can-you-get.md) 
  
5. Choose **Add new number** > **New user numbers**, and on the **Add new user numbers** page, choose the country/region, state/region, and city that you want to select numbers from.
    
6.  En **Cantidad**, escriba la cantidad de números de teléfono que desea para su organización desde esta área y, a continuación, haga clic en **Agregar** para crear una reserva.
    
    > [!CAUTION]
    > Tiene 10 minutos para seleccionar los números de teléfono. Después de 10 minutos, los teléfonos se devuelven al grupo de teléfonos de Office 365. 
  
    En la siguiente imagen, puede ver que agregué números de teléfono para dos ciudades diferentes y que me quedan 9 minutos para adquirirlos. 
    
     ![At the Add user numbers page, specify the area where you want to get the numbers for.](../images/f6dc1ef3-0bf2-4b4f-b32c-ca27e69c5553.png)
  
7. Puede elegir **Mostrar números** para ver la lista completa de números de teléfonos. Esto es útil si no quiere un número de teléfono específico de la lista.
    
8. Seleccione los números de teléfono que desee y elija **Adquirir números**.
    
9. Volverá a la página Voz en la que verá todos los números de teléfono adquiridos.
    
    ![At the Voice dashboard, you'll see all the phone numbers you acquired.](../images/4a9c681c-13f9-4cdc-a25b-93eb00d06b6c.png)
  
## <a name="step-3-add-emergency-addresses-and-locations-for-your-organization"></a>Paso 3: Agregar direcciones y ubicaciones de emergencia para la organización
<a name="bkmk_add_addresses"> </a>

1. En la página **Voz**, elija **Ubicaciones de emergencia** > **Agregar**.
    
2. En el panel **Nueva dirección**, introduzca un nombre para la dirección y, a continuación, complete los cuadros restantes.
    
     ![When you enter a new emergency address, the formatting of the street name might cause an error.](../images/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > Para los clientes que hablan inglés, si el nombre de la calle es un número, asegúrese de incluir "st" o "th" al final, como se muestra en la imagen anterior. 
  
3. Elija **Validar**.
    
    Si es necesario, se le pedirá que realice correcciones a la dirección. 
    
    > [!CAUTION]
    > Validar una dirección civil o postal implica asegurarse de que sea legítima y tenga el formato correcto. Es posible que una dirección de emergencia parcialmente correcta, por ejemplo con el nombre de la ciudad mal escrito, pueda seguir pasando como válida. Incluso si está mal escrita, pero pasó la validación, la combinación del nombre de la ciudad mal escrito junto con las demás partes correctas de la dirección constituye información suficiente para dirigir la llamada al centro de distribución emergencia correspondiente. 
  
    > [!TIP]
    > Si es necesario corregir la dirección para una respuesta de emergencia, se mostrará un banner verde que le informa que la dirección se ha actualizado. 
  
4. Después de validar la dirección, elija **Guardar**.
    
## <a name="step-4-assign-phone-numbers-and-emergency-addresses-to-users"></a>Paso 4: Asignar números de teléfono y direcciones de emergencia a los usuarios
<a name="bkmk_add_addresses"> </a>

> [!TIP]
> Si agrega más personas a la empresa justo antes de realizar este paso, es posible que demoren **varias horas** en aparecer en la página **Usuarios de voz**. Existe latencia.
  
1. En la página **Usuarios de voz**, elija la persona a la que quiera asignar un número de teléfono y una dirección de emergencia.
    
2. Elija **Asignar número**.
    
3. En la página **Asignar número**, en el menú desplegable **Seleccione el número que desea asignar**, seleccione el número de teléfono para el usuario.
    
4. Para seleccionar una dirección de emergencia, escriba el nombre de la ciudad en el cuadro **Buscar ciudad** y elija Buscar.
    
    > [!IMPORTANT]
    > Si se encuentra fuera de los Estados Unidos, los números ya tienen una dirección de emergencia, pero puede cambiarla ahora. Consulte [Asignar o cambiar la dirección de emergencia de un usuario](assign-or-change-an-emergency-address-for-a-user.md). 
  
5. Después de asignar el número de teléfono y la dirección de emergencia, elija **Guardar**.
    
## <a name="step-5-tell-your-users-about-their-new-phone-numbers"></a>Paso 5: Informar a los usuarios sus números de teléfono nuevos
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
    
- Si quiere más información sobre las direcciones de emergencia, vea [¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?](what-are-emergency-locations-addresses-and-call-routing.md)
    
## <a name="do-you-want-to-automate-assigning-phone-numbers"></a>¿Quiere automatizar la asignación de números de teléfono?
<a name="bkmk_add_addresses"> </a>

Si tiene experiencia con Windows PowerShell, puede usar los siguientes cmdlets para automatizar la asignación de números de teléfono a sus usuarios. 
  
- [Get-CsOnlineTelephoneNumber](https://technet.microsoft.com/en-us/library/mt243818.aspx): recupera los números de teléfono del Directorio de voz empresarial.
    
- [Set-CsOnlineVoiceUser](https://technet.microsoft.com/en-us/library/mt243817.aspx): configura los números de teléfono.
    
Para obtener más información, consulte [Referencia rápida:Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://technet.microsoft.com/en-us/library/dn362776%28v=ocs.15%29.aspx).
  
    > [!NOTE]
    > If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)

[Skype Empresarial Online: etiqueta de declinación de responsabilidades en llamadas de emergencia](https://go.microsoft.com/fwlink/?LinkID=692099)

## <a name="feedback"></a>¿Comentarios?
Para proporcionar comentarios sobre el producto o para hacernos saber cómo lo estamos haciendo, vea [Skype para comentarios de comercio](https://www.skypefeedback.com).