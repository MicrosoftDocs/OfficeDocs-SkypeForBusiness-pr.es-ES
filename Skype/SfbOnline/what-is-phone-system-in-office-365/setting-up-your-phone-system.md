---
title: Configuración de sistema de teléfono de la organización
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Aprenda a configurar el sistema de teléfono (PBX nube) para su organización. '
ms.openlocfilehash: 95fed9f26cefddce80de5c8f12a0e18d7368d1f4
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="setting-up-phone-system-in-your-organization"></a>Configuración de sistema de teléfono de la organización

La siguiente es una guía paso a paso para configurar el sistema de teléfono en Office 365. Vínculos a información detallada adicional están disponibles al final de cada paso.  

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Paso 1: Asegúrese de que el sistema telefónico está disponible en su país o región

1.  En primer lugar vaya a [disponibilidad de país y región para conferencias de Audio y planes de llamada](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)y seleccione su país o región en la lista en la parte superior de la página. 
2.  En **El sistema de teléfono**, revise la lista de características y detalles. 
3.  Si el sistema telefónico está disponible, vaya al paso 2. 

**Para obtener más información acerca de la disponibilidad regional de sistema de teléfono y conferencias de Audio, ver la [disponibilidad de país y región para conferencias de Audio y llamar a los planes](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Paso 2: Comprar y asignar licencias de sistema telefónico y Plan de llamadas

Para asignar una licencia de sistema telefónico y Plan de llamadas a un único usuario, los pasos son lo mismo que asignar una licencia de Office 365. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Si desea asignar varios usuarios de forma masiva, vea (.. / skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Paso 3: Obtener números de teléfono de los usuarios

[] Para poder configurar los usuarios de su organización para que puedan recibir y realizar llamadas telefónicas, debe usar el Centro de administración de Skype Empresarial para obtener los números de teléfono. 

Existen tres maneras de obtener números para los usuarios: 
- Obtener números nuevos con el Centro de administración de Skype Empresarial.
- Obtener nuevos números que no están disponibles en el Skype para el centro de administración de negocios.
- Realizar la portabilidad de los números existentes de su proveedor de servicios u operador telefónico actual, o transferirlos.

Debe usar la página **Números nuevos** para ver, buscar, adquirir y reservar dichos números. Puede buscar por ciudad, estado y país o región y, a continuación, escriba el número de números de teléfono que necesitará para los usuarios. 

### <a name="get-new-user-phone-numbers"></a>Obtener nuevos números de teléfono del usuario 
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la exploración de la izquierda vaya a **voz** > **números de teléfono**, haga clic en **Agregar nuevo número** ![botón Agregar](../images/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)y, a continuación, haga clic en **los números de usuario nuevo**.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtener nuevos números que no están disponibles en el Skype para el centro de administración de negocios
  
A veces (dependiendo de su país o región) no podrá obtener los números de nuevo usando el Skype para el centro de administración de negocios. En este caso, necesitará descargar un formulario y envíela a nosotros. Consulte [administrar números de teléfono de la organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para obtener información sobre cómo solicitar nuevos números de usuario.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Realizar la portabilidad de los números de su proveedor de servicios u operador telefónico o transferirlos
  
- Si necesita 999 o menos números de teléfono para sus usuarios, puede usar el asistente para la **Solicitud de portabilidad de nuevo número local** del Centro de administración de Skype Empresarial. Siga los pasos descritos en los [números de teléfono de transferencia a Office 365](..//what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) para transferir sobre sus números de teléfono a Skype para los negocios en línea.
    
- Si necesita más de 999 números de teléfono de puerto, consulte [administrar números de teléfono de la organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para enviar una solicitud de servicio del pedido de puerto o el orden para obtener todos estos números de teléfono trasladados a Office 365. 

**Para obtener información detallada acerca de cómo obtener nuevos números de teléfono o transferir los números existentes, vea [administrar números de teléfono para su organización](../what-are-calling-plans-in-office-365\manage-phone-numbers-for-your-organization\manage-phone-numbers-for-your-organization.md).**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Paso 4: Obtener números de teléfono de servicio (audioconferencias, colas de llamadas, operadores automáticos)

Además de obtener números de teléfono para los usuarios de Office 365, puede buscar y adquirir el número o números de teléfono gratuitos para servicios tales como colas de llamada (también denominadas números de servicio), operadores automáticos y conferencias de audio (para puentes de conferencia). Los números de teléfono de servicio tienen una mayor capacidad de llamadas simultáneas que los números de teléfono de usuario o suscriptor. Por ejemplo, un número de servicio puede controlar 100s de llamadas simultáneamente, mientras que el número de teléfono de un usuario sólo puede controlar varias llamadas simultáneamente.

### <a name="get-new-service-numbers"></a>Obtener nuevos números de servicio

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la exploración de la izquierda vaya a **voz** > **números de teléfono** > **Agregar nuevo número**y, a continuación, haga clic en **los números de servicio nuevo**.
    
    > [!IMPORTANT] 
    > Para que poder ver la opción de **voz** en la exploración de la izquierda en el Skype para el centro de administración de negocios, primero debe comprar una licencia adicional para **Conferencias de Audio** , una licencia del módulo de **Sistema de teléfono** o al menos una **licencia Enterprise E5**.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtener nuevos números que no están disponibles en el Skype para el centro de administración de negocios
  
A veces (dependiendo de su país o región) no podrá obtener los números de nuevo usando el Skype para el centro de administración de negocios. En este caso, necesitará descargar un formulario y envíela a nosotros. Consulte [administrar números de teléfono de la organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para aprender a solicitar nuevos números. 

### <a name="port-or-transfer-existing-service-numbers"></a>Portabilidad o trasferencia de números de servicio existentes

Si quiere transferir números de servicio de su proveedor de servicios u operador de telefonía actual, debe enviar manualmente una solicitud de portabilidad a Microsoft. Tiene que enviar los pedidos de puerto diferente para cada tipo de número de servicio (pago VS gratuito) que se va a transferir utilizando una carta de autorización (LOA). En la carta de autorización (LOA), debe seleccionar el tipo correcto de número de servicio. Al ponerse en contacto con el soporte técnico de Microsoft, asegúrese de que especificar que va a transferir un número de servicio (*y no un número de suscriptor o usuario*) o la capacidad concurrente de llamada puede no ser suficiente para manejar volúmenes de llamada. Si desea transferir los números de teléfono o hacer otras cosas con sus números de teléfono, vea [administrar números de teléfono para su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Paso 5: Si desea configurar planes de llamada

Si se han seguido los pasos anteriores, ya ha comprado y ha asignado el sistema telefónico y licencias y un Plan de llamada (paso 2) y adquirido los números de teléfono para los usuarios (paso 3), por lo que su plan de llamadas parcial está configurado. Siga los tres procedimientos siguientes para completar la configuración de tu Plan de llamadas.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>Agregar direcciones de emergencia y ubicaciones para su organización

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
    
### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>Asigne números de teléfono y direcciones de emergencia a los usuarios

> [!TIP]
> Si agrega más personas a la empresa justo antes de realizar este paso, es posible que demoren **varias horas** en aparecer en la página **Usuarios de voz**. Existe latencia.
  
1. En la página **Usuarios de voz**, elija la persona a la que quiera asignar un número de teléfono y una dirección de emergencia.
    
2. Elija **Asignar número**.
    
3. En la página **Asignar número**, en el menú desplegable **Seleccione el número que desea asignar**, seleccione el número de teléfono para el usuario.
    
4. Para seleccionar una dirección de emergencia, escriba el nombre de la ciudad en el cuadro **Buscar ciudad** y elija Buscar.
    
    > [!IMPORTANT]
    > Si se encuentra fuera de los Estados Unidos, los números ya tienen una dirección de emergencia, pero puede cambiarla ahora. Consulte [Asignar o cambiar la dirección de emergencia de un usuario](../what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user.md). 
  
5. Después de asignar el número de teléfono y la dirección de emergencia, elija **Guardar**.
    
### <a name="tell-your-users-about-their-new-phone-numbers"></a>Indique a los usuarios acerca de sus nuevos números de teléfono


Recomendamos enviar correo o usar el método de comunicación preferido de su empresa para informar a sus miembros los nuevos números de teléfono. 

Le mostramos cómo pueden ver ese número de teléfono en su aplicación de **Skype para empresas** :
  
1. Inicie sesión en Skype Empresarial en el escritorio.
    
2. Elija **Configuración** > **Herramientas** > **Opciones**. 
    
     ![To view your phone number, go to Settings > Tools > Options.](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. A continuación, elija **Teléfonos**. 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
En los **Equipos de Microsoft**, los usuarios pueden ver su número de teléfono haciendo clic en **llamadas** en la exploración de la izquierda. El número de teléfono se muestra encima del teclado.

![Un usuario puede ver su número de Teams de Microsoft haciendo clic en llamadas en la exploración de la izquierda.](../images/teams-phone-number.png)

**Para obtener más información acerca de todos los pasos necesarios para configurar un Plan de llamadas, consulte [Configurar planes de llamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Paso 6: Si desea establecer una conferencia de Audio

En algunas ocasiones, en su organización se necesitará un teléfono para llamar a una reunión. Skype para empresas y Teams de Microsoft incluyen la característica de conferencia de audio sólo esta situación! La gente puede llamar a Skype para reuniones de negocios o Teams de Microsoft mediante un teléfono, en lugar de utilizar el Skype para negocios o Teams de Microsoft de la aplicación en un dispositivo móvil o PC. 
  
Sólo debe configurar conferencias de Audio para las personas que va a programar o cliente potencial de las reuniones. Asistentes a la reunión que se conectan telefónicamente no necesitan cualquier licencias asignadas a las mismas o a otro programa de instalación.
  
Para las preguntas más frecuentes acerca de las conferencias de Audio, consulte [las preguntas más frecuentes de conferencia de Audio](../audio-conferencing-in-office-365/audio-conferencing-common-questions.md).
    
1. Si ha adquirido licencias de complemento de **Conferencias de Audio** y comunicaciones créditos, asignarles demasiado. Para obtener instrucciones, consulte [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

    Decidir en el proveedor de conferencia de audio. Un proveedor de conferencia de audio proporciona un puente de conferencia de audio. El puente de conferencia establece sus números de teléfono de acceso telefónico, pasadores y conferencia identificadores para las reuniones. Decida si desea utilizar Microsoft o un proveedor de conferencia de audio de terceros: 

    > [!NOTE]
    > Los usuarios de Microsoft Teams no usuario un proveedor de conferencia de audio de terceros. 
  
    - **Microsoft como proveedor de conferencia de audio**: si desea que la solución más sencilla para conferencias de audio, elija Microsoft como proveedor de conferencia de audio.
    
    - **Otros fabricantes como proveedor de conferencia de audio**: Si estás en un país donde no está disponible en Office 365 conferencias de Audio, la calidad de servicio no es gran cosa debido a su ubicación o tiene un contrato existente, elija un audio de otros fabricantes proveedor de conferencia. Para buscar un proveedor, visite [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).
 
2.  Asigne al proveedor de conferencia de audio para las personas que conducen o programan reuniones. Consulte [Asignar Microsoft como proveedor de conferencia de audio](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).

3. Configurar las invitaciones a reuniones. Los pasos siguientes son opcionales, pero muchas administradores como para llevarlas a cabo: 
  
    1. [Personalizar invitaciones a reuniones](../set-up-skype-for-business-online/customize-meeting-invitations.md). Los números de acceso telefónico que se establecen para el usuario se agregan automáticamente a las invitaciones de las reuniones que se envían a los asistentes. Sin embargo, puede agregar su propia ayuda y vínculos jurídicos, un mensaje de texto y gráfico de pequeña empresa.
    
    2. [Conjunto de números de teléfono de conferencia de Audio de organizadores que están incluidos en las invitaciones de la reunión](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md). Esto es el número de teléfono que se mostrará en la reunión programada por el usuario.
    
    3. [Idiomas de operador automático para conferencias de Audio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que utiliza el operador automático de conferencia de audio para saludar a un llamador cuando llama a un número de teléfono de conferencia de Audio. Este paso sólo se aplica si está utilizando Microsoft como proveedor de audio.
    
    4. [Establecer la longitud del perno para las reuniones de conferencia de Audio](../audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings.md).
    
    > [!NOTE]
    > Esta característica no está todavía disponible para los clientes mediante Office 365 operado por 21Vianet en China. Para obtener más información, consulte [Obtenga información acerca de Office 365 operado por 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE). 

**Para obtener más información acerca de las conferencias de Audio, consulte [configurar las conferencias de Audio](../audio-conferencing-in-office-365/set-up-audio-conferencing.md).**

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a>Paso 7: Si desea configurar una cola de llamadas de sistema de teléfono

Llamada de sistema incluyen un saludo que se utiliza cuando alguien llama a un número de teléfono para su organización, la capacidad para colocar automáticamente las llamadas en espera y la capacidad de búsqueda para el siguiente agente de llamada disponible controlar la llamada, mientras que la gente que llamada se escucha música en espera. Puede crear una o varias colas de llamada para su organización.

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. Después de obtener el número o números de teléfono de servicio gratuito, se mostrará en **Skype para el centro de administración de negocios** > **voz** > **números de teléfono**y la voluntad de **tipo número** en la lista aparecen como **servicio - gratis **. Para obtener los números de servicio, vea [números de teléfono de servicio de obtención de Skype para empresas y equipos de Microsoft](getting-service-phone-numbers.md) o si desea transferir y el número de servicio existente, consulte [transferir números de teléfono para Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si está fuera de los Estados Unidos, no puede utilizar el Skype para el centro de administración de negocios para obtener números de servicio. Vaya a [administrar números de teléfono de la organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo desde fuera de Estados Unidos.

Para crear una nueva cola de llamadas en el **Skype para el centro de administración de negocios**, haga clic en **enrutamiento de llamadas** > **llamar a las colas**, haga clic en **Agregar nuevo**y, a continuación, siga las instrucciones en el **paso 3** de [crear una cola de llamada del sistema telefónico]( create-a-phone-system-call-queue.md#step-3---create-a-new-call-queue).

**Para obtener más detalles acerca de las colas de llamada, vea [crear una cola de llamada del sistema telefónico](create-a-phone-system-call-queue.md).**

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a>Paso 8: Si desea configurar un sistema de teléfono automática de operador

Operadores automáticos permiten a los usuarios que llaman a su organización y navegar por un sistema de menús para obtenerlos en el departamento correcto, llame a la cola, la persona o el operador. Puede crear a un operador automático para su organización mediante el Skype para el centro de administración de negocios. 

Para crear un nuevo operador automático, en el Skype para el centro de administración de negocios, haga clic en **enrutamiento de llamadas** > **operadores automáticos**, haga clic en **Agregar nuevo**y, a continuación, siga las instrucciones de cada página en el **paso 2** del [conjunto de un sistema de teléfono auto operador](set-up-a-phone-system-auto-attendant.md#step-2---create-a-new-auto-attendant).

**Para obtener más detalles acerca de los operadores de sistema de teléfono automáticos, consulte [configurar un operador automático de sistema de teléfono](set-up-a-phone-system-auto-attendant.md).**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Paso 9: Asignar números de teléfono de servicio (audioconferencias, colas de llamadas, operadores automáticos)

Una vez que tenga los números de servicio desde el **paso 4 anteriormente**, debe asignar a cada tipo de servicio que desee. Por ejemplo, si desea un número de teléfono de servicio dedicado (pago o gratuito), debe asignar el número para el puente de conferencia.

- Para conferencias de Audio, puede asignar un número dedicado a un puente de conferencia yendo al **Centro de administración de Office 365** > **centra Admin** > **Skype for Business** > **conferencias de Audio** y haga clic en el puente de conferencia o viendo [cambiar el número o números gratuitos en el puente de conferencia de Audio](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- Para operadores automáticos, puede asignar un número dedicado a un operador automático yendo al **Centro de administración de Office 365** > **centra Admin** > **Skype for Business** > **enrutamiento de llamadas** > **Auto attendants **y haga clic en el operador automático. En la página **General** , el número de servicio ya tiene will aparecerán en el **número de teléfono** de la lista desplegable. Para obtener más información, consulte [configurar un Operador automático de sistema de teléfono](set-up-a-phone-system-auto-attendant.md).

- Para llamar a las colas, puede asignar un número dedicado a una cola de llamada yendo al **Centro de administración de Office 365** > **centra Admin** > **Skype for Business** > **enrutamiento de llamadas** > **llamar a colas** y haga clic en la cola de llamada. En la página **General** , el número de servicio ya tiene will aparecerán en el **número de teléfono** de la lista desplegable. Para obtener información detallada, vea [crear una cola de llamada del sistema telefónico](create-a-phone-system-call-queue.md).

**Para obtener información detallada sobre cómo obtener los nuevos números de servicio y trasladar los números de servicio existentes, vea [números de teléfono del servicio de obtención](getting-service-phone-numbers.md).**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Paso 10: Configurar comunicaciones créditos para su organización

Necesitará configurar comunicaciones créditos si desea utilizar números gratuitos con Skype para empresas y Teams de Microsoft. Asimismo, recomendamos que configura créditos de comunicaciones para sus planes de llamada (nacionales o internacionales) y conferencias de Audio los usuarios que necesitan la capacidad de llamar a **cualquier destino**. Muchos países o regiones se incluyen, pero algunos destinos pueden no incluirse en las suscripciones de su Plan de llamadas o conferencias de Audio. Si no configurar Facturación de créditos de comunicaciones y asignar una licencia de **Créditos de comunicaciones** a los usuarios y ejecutar minutos para su organización (dependiendo del Plan de llamada o conferencia de Audio plan en su país o región), los usuarios no podrá realizar llamadas o marcar de las reuniones de conferencia de Audio. Puede obtener más información, recomienda incluir financiación importes, leyendo [¿qué comunicaciones créditos?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)
  
> [!NOTE]
> Para averiguar cuánto cuestan, [Consulte aquí las tarifas](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 

### <a name="to-set-up-communications-credits"></a>Para configurar las comunicaciones créditos 

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. En la izquierda de la navegación en el centro de administración de Office 365, vaya a **facturación** > **suscripciones** > **complementos** > **comprar complementos**y a continuación, elija **Comunicaciones créditos** > **comprar ahora**.
    
3. En la página de suscripción de **Créditos de comunicaciones** , rellene la información y, a continuación, haga clic en **siguiente**.
        
4. Introduzca su información de pago y haga clic en **realizar pedido**.
    >[!IMPORTANT]
    >Si eres un cliente de licencias por volumen, puede elegir el número de contrato de la empresa para el pago. Si tiene varios números de contrato enterprise, podrá seleccionar qué acuerdo de empresa que desea utilizar para el pago. También tendrá oportunidad de especificar un número de orden de compra para asociar con el número de contrato enterprise (si procede).
    
**Para obtener más información acerca de cómo configurar comunicaciones créditos, consulte [Configurar comunicaciones créditos para su organización](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).**
  
### <a name="assign-a-communications-credits-license-to-users"></a>Asignar una licencia de créditos de comunicaciones a los usuarios

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. En la izquierda de la navegación en el centro de administración de Office 365, vaya a **usuarios** > **usuarios activos**y, a continuación, seleccione uno o varios usuarios de la lista.
    
3. En el panel de acciones, en **Licencia asignada**, haga clic en **Editar**.
    
4. En la página de **licencias del producto** , alternar ** comunicaciones créditos ** **en** asignar esta licencia y, a continuación, haga clic en **Guardar**.
    
    > [!NOTE]
    > Incluso si tiene usuarios que están asignados a una licencia de **Enterprise E5** , todavía se recomienda que lo haga.

**Para obtener más información acerca de asignar licencias de créditos de comunicaciones, vea [Configurar comunicaciones créditos para su organización](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).**

## <a name="related-topics"></a>See also
[Esto es lo que conseguirá con Sistema telefónico en Office 365](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 