---
title: Configurar el Sistema telefónico en su organización
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Obtenga información sobre cómo configurar el sistema telefónico (PBX en la nube) para su organización. '
ms.openlocfilehash: 7a180817fb4a3885748a5ca80c494ef1b69143a4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32205551"
---
# <a name="setting-up-phone-system-in-your-organization"></a>Configurar el Sistema telefónico en su organización

The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Paso 1: asegurarse de que el sistema telefónico está disponible en su país o región

1.  En primer lugar vaya a [Disponibilidad de país y región para los planes de audioconferencia y llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) y seleccione su país o región en la lista de la parte superior de la página. 
2.  Bajo **Sistema telefónico**, revise la lista de las características y los detalles. 
3.  Si el sistema telefónico está disponible, vaya al paso 2. 

**Para obtener más información acerca de la disponibilidad regional del sistema telefónico y de la audioconferencia, consulte [Disponibilidad de país y región para los planes de audioconferencia y llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Paso 2: comprar y asignar licencias del sistema telefónico y del plan de llamadas

Para asignar una licencia del sistema telefónico y del plan de llamadas a un solo usuario los pasos son los mismos que para asignar una licencia de Office 365. Vea [las licencias de asignar los equipos de Microsoft](assign-teams-licenses.md). Si desea asignar a varios usuarios de forma masiva, vea [licencias de asignar los equipos de Microsoft](assign-teams-licenses.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Paso 3: Obtener los números de teléfono para los usuarios

[] Para poder configurar los usuarios de su organización para que puedan recibir y realizar llamadas telefónicas, debe usar el Centro de administración de Skype Empresarial para obtener los números de teléfono.

Existen tres maneras de obtener números para los usuarios:
- Get new numbers using the Skype for Business admin center.
- Obtener números nuevos que no están disponibles en el centro de administración de Skype for Business.
- Realizar la portabilidad de los números existentes de su proveedor de servicios u operador telefónico actual, o transferirlos.

You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.

### <a name="get-new-user-phone-numbers"></a>Obtener los nuevos números de teléfono del usuario 
 
![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el panel de navegación izquierdo, vaya a **voz** > **los números de teléfono**, haga clic en **Agregar nuevo número** ![botón Agregar](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)y, a continuación, haga clic en **nuevo usuario los números**.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtener números nuevos que no están disponibles en el centro de administración de Skype for Business
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Port or transfer phone numbers from your service provider or phone carrier
  
- If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center. Follow the steps found in [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.
    
- Si necesita más de 999 números de teléfono de puerto, vea [administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para enviar una solicitud de servicio de orden de puerto o el orden para obtener todos estos números de teléfono que se pongan en puerto a Office 365. 

**Para obtener información detallada acerca de la obtención de nuevos números de teléfono o sobre transferir los números existentes, consulte [Administrar los números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Paso 4: obtener los números de teléfono de servicio (audioconferencia, colas de llamadas, operadores automáticos)

In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.

### <a name="get-new-service-numbers"></a>Obtener nuevos números de servicio

![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**


1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.

3. En el panel de navegación izquierdo, vaya a **voz** > **los números de teléfono** > **Agregar nuevo número**y, a continuación, haga clic en **los números de servicio nueva**.

    > [!IMPORTANT]
    > Para que pueda ver la opción de **voz** en la izquierda en la Skype para el centro de administración de negocio, primero debe comprar una licencia adicional para **Conferencias de Audio** , una licencia adicional para **El sistema de teléfono** o al menos una **licencia Enterprise E5**.

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtener números nuevos que no están disponibles en el centro de administración de Skype for Business
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers. 

### <a name="port-or-transfer-existing-service-numbers"></a>Portabilidad o trasferencia de números de servicio existentes

If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Paso 5: si desea configurar planes de llamadas

If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>Agregar direcciones de emergencias y ubicaciones para su organización

1. En la página **Voz**, elija **Ubicaciones de emergencia** > **Agregar**.

2. En el panel **Nueva dirección**, introduzca un nombre para la dirección y, a continuación, complete los cuadros restantes.
    
     ![Al escribir una dirección de emergencia nueva, el formato del nombre de la calle puede provocar un error.](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > Para los clientes que hablan inglés, si el nombre de la calle es un número, asegúrese de incluir "st" o "th" al final, como se muestra en la imagen anterior.

3. Elija **Validar**.

    Si es necesario, se le pedirá que realice correcciones a la dirección.

    > [!CAUTION]
    > Validar una dirección civil o postal implica asegurarse de que sea legítima y tenga el formato correcto. Es posible que una dirección de emergencia parcialmente correcta, por ejemplo con el nombre de la ciudad mal escrito, pueda seguir pasando como válida. Incluso si está mal escrita, pero pasó la validación, la combinación del nombre de la ciudad mal escrito junto con las demás partes correctas de la dirección constituye información suficiente para dirigir la llamada al centro de distribución emergencia correspondiente.

    > [!TIP]
    > Si es necesario corregir la dirección para una respuesta de emergencia, se mostrará un banner verde que le informa que la dirección se ha actualizado.

4. Después de validar la dirección, elija **Guardar**.

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>Asigne números de teléfono y direcciones de emergencia a los usuarios

> [!TIP]
> Si agrega más personas a la empresa justo antes de realizar este paso, es posible que demoren **varias horas** en aparecer en la página **Usuarios de voz**. Existe latencia.

1. En la página **Usuarios de voz**, elija la persona a la que quiera asignar un número de teléfono y una dirección de emergencia.

2. Elija **Asignar número**.

3. En la página **Asignar número**, en el menú desplegable **Seleccione el número que desea asignar**, seleccione el número de teléfono para el usuario.

4. Para seleccionar una dirección de emergencia, escriba el nombre de la ciudad en el cuadro **Buscar ciudad** y elija Buscar.

    > [!IMPORTANT]
    > Si se encuentra fuera de los Estados Unidos, los números ya tienen una dirección de emergencia, pero puede cambiarla ahora. Consulte [Asignar o cambiar la dirección de emergencia de un usuario](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user). 
  
5. Después de asignar el número de teléfono y la dirección de emergencia, elija **Guardar**.

### <a name="tell-your-users-about-their-new-phone-numbers"></a>Indique a los usuarios acerca de sus números de teléfono nuevo


Recomendamos enviar correo o usar el método de comunicación preferido de su empresa para informar a sus miembros los nuevos números de teléfono.

Aquí es cómo pueden ver ese número de teléfono en su aplicación de **Skype para la empresa** :

1. Inicie sesión en Skype Empresarial en el escritorio.
    
2. Elija **Configuración** > **Herramientas** > **Opciones**. 
    
     ![Para ver su número de teléfono, vaya a Configuración > Herramientas > Opciones.](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. A continuación, elija **Teléfonos**. 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.

![Un usuario puede ver su número en Microsoft Teams haciendo clic en Llamadas en el panel de navegación izquierdo.](media/teams-phone-number.png)

**Para obtener información más detallada acerca de todos los pasos necesarios para configurar un plan de llamadas, consulte [Configurar planes de llamadas](set-up-calling-plans.md).**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Paso 6: si desea configurar la audioconferencia

Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.

You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Para ver las preguntas más frecuentes acerca de las audioconferencias, consulte [Preguntas frecuentes sobre audioconferencias](audio-conferencing-common-questions.md).
    
1. Si ha comprado licencias del complemento de **audioconferencia** y licencias de créditos de comunicaciones, asígnelas también. Para obtener instrucciones, vea [licencias de asignar los equipos de Microsoft](assign-teams-licenses.md).

    Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider:

    > [!NOTE]
    > Los usuarios de Microsoft Teams no usuario un proveedor de conferencia de audio de terceros.

    - **Microsoft como su proveedor de audioconferencias**: si busca la solución más sencilla, elija a Microsoft como su proveedor de audioconferencias.
    
    - **Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).
 
2. Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

3. Set up meeting invitations. The following steps are optional, but a lot of admins like to do them: 
  
   1. [Personalizar invitaciones a reuniones en Skype para la empresa](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations). Los números de acceso telefónico que se establecen para el usuario se agregan automáticamente a las invitaciones de las reuniones que se envían a los asistentes. Sin embargo, puede agregar sus propios vínculos de ayuda y de avisos legales, un mensaje de texto y un pequeño distintivo gráfico de la empresa.
    
   2. Establecer los números de teléfono de conferencia de Audio para los organizadores que están incluidos en la reunión invitaciones [en Skype para la empresa](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) o [en los equipos de Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md). Este es el número de teléfono que se mostrará en la reunión que está programada por el usuario.
    
   3. Establecer los idiomas de operador automático para conferencias de Audio [en Skype para la empresa](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) o [en los equipos de Microsoft](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) que usa el operador automático de conferencia de audio para saludar a un autor de la llamada al conectarse a un número de teléfono de conferencia de Audio. Este paso solo se aplica si está utilizando Microsoft como su proveedor de audioconferencias.
    
   4. Establecer la longitud del eje para las reuniones de conferencia de Audio [en los equipos de Microsoft](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md).
    
      > [!NOTE]
      > This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).

**Para obtener más información acerca de las conferencias de Audio, consulte [Configurar conferencias de Audio para los equipos de Microsoft](set-up-audio-conferencing-in-teams.md).**

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>Paso 7: Si desea configurar una cola de llamada de nube

Colas de llamada de nube incluyen el saludo que se usa cuando alguien llama a un número de teléfono para su organización, la capacidad de poner automáticamente las llamadas en espera y la capacidad de búsqueda para el siguiente agente de llamada disponibles controlar la llamada mientras las personas que son de llamada escucha música en espera. Puede crear una o varias colas de llamadas para su organización.

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.

Para crear una nueva cola de llamadas, en el **Skype para el centro de administración de negocio**, haga clic en **enrutamiento de llamadas** > **colas de llamadas**, haga clic en **Agregar nuevo**y, a continuación, siga las instrucciones que aparecen en el **paso 3** de [creación de una cola de llamada en la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue).

**Para obtener más información acerca de las colas de llamadas, vea [crear una cola de llamada en la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).**

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>Paso 8: Si desea configurar una nube de operador automático

Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center.

Para crear un nuevo operador automático, en el Skype para el centro de administración de negocio, haga clic en **enrutamiento de llamadas** > **operadores automáticos**, haga clic en **Agregar nuevo**y, a continuación, siga las instrucciones para cada página en el **paso 2** de [conjunto de copia de seguridad un operador automático de la nube ](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).

**Para obtener más información sobre los operadores automáticos en la nube, consulte [configurar un operador automático de la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Paso 9: asignar los números de teléfono de servicio (audioconferencia, colas de llamadas, operadores automáticos)

Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want. For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.

- Para audioconferencias, puede asignar un número dedicado a un puente de conferencias yendo al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Audioconferencias** y haciendo clic en el puente de conferencia, o consultando [Cambiar los números de teléfono de pago o gratuitos en su puente de audioconferencias](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- Para los operadores automáticos, puede asignar un número dedicado a un operador automático yendo al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Enrutamiento de llamadas** > **Operadores automáticos** y haciendo clic en el operador automático. En la página **General**, el número de servicio que ya tenga aparecerá en la lista desplegable **Número de teléfono**. Para obtener información detallada, vea [configurar un operador automático de la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).

- En el caso de las colas de llamadas, puede asignar un número dedicado a una de ellas yendo al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Enrutamiento de llamadas** > **Colas de llamadas** y haciendo clic en la cola de llamadas. En la página **General**, el número de servicio que ya tenga aparecerá en la lista desplegable **Número de teléfono**. Para obtener información detallada, vea [crear una cola de llamada en la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

**Para ver información detallada sobre cómo obtener nuevos números de servicio y hacer la portabilidad de otros ya existentes, consulte [Obtener números de teléfono de servicio](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers).**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Paso 10: Configurar Communications créditos para su organización

You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)
  
> [!NOTE]
> Para saber cuánto cuesta, [consulte aquí las tarifas](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).

### <a name="to-set-up-communications-credits"></a>Configurar créditos de comunicaciones

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. En el panel de navegación izquierdo del centro de administración de Office 365, vaya a **Facturación** > **Suscripciones** > **Complementos** > **Comprar complementos**, y a continuación elija **Créditos de comunicaciones** > **Comprar ahora**.

3. En la página de suscripción de los **Créditos de comunicaciones**, rellene la información y después haga clic en **Siguiente**.

4. Escriba la información de pago y haga clic en **Realizar pedido**.
    >[!IMPORTANT]
    >If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).
    
**Para obtener información más detallada acerca de cómo configurar créditos de comunicaciones, consulte [Configurar créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).**
  
### <a name="assign-a-communications-credits-license-to-users"></a>Asignar una licencia de créditos de comunicaciones a los usuarios

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. En la izquierda el centro de administración de Office 365, vaya a **los usuarios** > **usuarios activos**y, a continuación, seleccione un usuario o usuarios de la lista.

3. En el panel de acciones, en **Licencias de productos**, haga clic en **Editar**.

4. En la página **licencias de producto** , alternar **Communications créditos** **en** para asignar esta licencia y, a continuación, haga clic en **Guardar**.

    > [!NOTE]
    > Incluso si tiene usuarios que tengan asignados una licencia **Enterprise E5** , sigue siendo recomendable hacer esto.

**Para obtener más información acerca de la asignación de licencias de créditos de comunicaciones, consulte [Configurar créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).**

## <a name="related-topics"></a>Temas relacionados
[Esto es lo obtiene con el Sistema telefónico de Office 365](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
