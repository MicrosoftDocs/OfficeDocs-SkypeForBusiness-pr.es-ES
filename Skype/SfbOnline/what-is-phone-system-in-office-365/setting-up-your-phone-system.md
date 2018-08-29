---
title: Configurar un sistema telefónico en su organización
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
- Phone System
description: 'Obtener información sobre cómo configurar un sistema telefónico (PBX en la nube) para su organización. '
ms.openlocfilehash: 2566bfcef892767f89afb28643deb91942596e76
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244634"
---
# <a name="setting-up-phone-system-in-your-organization"></a>Configurar un sistema telefónico en su organización

Lo siguiente es una guía paso a paso para configurar un sistema telefónico en Office 365. Hay vínculos a información detallada adicional disponibles al final de cada paso.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Paso 1: asegurarse de que el sistema telefónico está disponible en su país o región

1.  En primer lugar vaya a [Disponibilidad de país y región para los planes de audioconferencia y llamadas](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) y seleccione su país o región en la lista de la parte superior de la página.
2.  Bajo **Sistema telefónico**, revise la lista de las características y los detalles.
3.  Si el sistema telefónico está disponible, vaya al paso 2.

**Para obtener más información acerca de la disponibilidad regional del sistema telefónico y de la audioconferencia, consulte [Disponibilidad de país y región para los planes de audioconferencia y llamadas](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Paso 2: comprar y asignar licencias del sistema telefónico y del plan de llamadas

Para asignar una licencia del sistema telefónico y del plan de llamadas a un solo usuario los pasos son los mismos que para asignar una licencia de Office 365. Consulte [Asignar licencias de Skype for Business y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Si desea asignar varios usuarios en masa, consulte [Asignar licencias de Skype for Business y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Paso 3: obtener números de teléfono para los usuarios

Antes de poder configurar los usuarios de su organización para que puedan recibir y realizar llamadas telefónicas, debe conseguirles un número de teléfono.

Hay tres formas de obtener los números para los usuarios:
- Obtener números nuevos mediante el centro de administración de Skype for Business.
- Obtener números nuevos que no están disponibles en el centro de administración de Skype for Business.
- Realizar la portabilidad a Office 365 de los números existentes de su proveedor de servicios u operador telefónico actual, o transferirlos.

Debe usar la página **Agregar nuevos números de usuario** para ver, buscar, adquirir y reservar dichos números. Puede buscar por País/Región, Estado o Ciudad y, a continuación, escribir la cantidad de números de teléfono que necesitará para los usuarios.

### <a name="get-new-user-phone-numbers"></a>Obtener nuevos números de teléfono de usuario

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usando el centro de administración de Skype for Business**


1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya a **Centro de administración de Office 365** > **Skype for Business**.

3. En el panel de navegación de la izquierda, vaya a **Voz** > **Números de teléfono**, haga clic en **Agregar nuevo número** ![Botón agregar](../images/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png), y luego haga clic en **Nuevos números de usuario**.

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtener números nuevos que no están disponibles en el centro de administración de Skype for Business

A veces (dependiendo de su país o región) no podrá obtener sus números nuevos utilizando el centro de administración de Skype for Business. En ese caso, necesitará descargar un formulario y enviárnoslo de vuelta. Consulte [Administrar los números de teléfono de su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para aprender a solicitar nuevos números de usuario.

### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Realizar la portabilidad de los números de su proveedor de servicios u operador telefónico, o transferirlos

- Si necesita 999 o menos números de teléfono para sus usuarios, puede usar el asistente para la **Solicitud de portabilidad de nuevo número local** del Centro de administración de Skype Empresarial. Siga los pasos que se indican en [Transferir números de teléfono a Office 365](..//what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) para transferir los números de teléfono a Skype for Business Online.

- Si necesita hacer la portabilidad de más de 999 números de teléfono, consulte [Administrar los números de teléfono de su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para enviar una solicitud de portabilidad del servicio, u ordene que se haga la portabilidad de todos esos números de teléfono a Office 365.

**Para obtener información detallada acerca de la obtención de nuevos números de teléfono o sobre transferir los números existentes, consulte [Administrar los números de teléfono de su organización](../what-are-calling-plans-in-office-365\manage-phone-numbers-for-your-organization\manage-phone-numbers-for-your-organization.md).**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Paso 4: obtener los números de teléfono de servicio (audioconferencia, colas de llamadas, operadores automáticos)

Además de obtener los números de teléfono para los usuarios de Office 365, puede buscar y adquirir números de teléfono de pago o gratuitos para servicios como audioconferencias (para puentes de conferencias), operadores automáticos y colas de llamadas (también denominados números de servicio). Los números de teléfono de servicio tienen una mayor capacidad de llamadas simultáneas que los números de teléfono de usuario o de suscriptor. Por ejemplo, un número de servicio puede gestionar cientos de llamadas a la vez, mientras que un número de teléfono de usuario solo puede admitir unas pocas al mismo tiempo.

### <a name="get-new-service-numbers"></a>Obtener nuevos números de servicio

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usando el centro de administración de Skype for Business**


1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya a **Centro de administración de Office 365** > **Skype for Business**.

3. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono** > **Agregar nuevo número** y, a continuación, haga clic en **Nuevos números de servicio**.

    > [!IMPORTANT]
    > Para poder ver la opción **Voz** en el panel de navegación izquierdo del Centro de administración de Skype for Business, primero tiene que adquirir como mínimo una **licencia de Enterprise E5**, una licencia del complemento **Sistema telefónico** o una licencia del complemento **Audioconferencia**.

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtener números nuevos que no están disponibles en el centro de administración de Skype for Business

A veces (dependiendo de su país o región) no podrá obtener sus números nuevos utilizando el centro de administración de Skype for Business. En ese caso, necesitará descargar un formulario y enviárnoslo de vuelta. Consulte [Administrar los números de teléfono de su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para aprender a solicitar números nuevos.

### <a name="port-or-transfer-existing-service-numbers"></a>Realizar la portabilidad o la trasferencia de números de servicio existentes

Si quiere transferir números de servicio de su proveedor de servicios u operador de telefonía actual, debe enviar manualmente una solicitud de portabilidad a Microsoft. Tiene que presentar solicitudes de portabilidad separadas para cada tipo de número de servicio (de pago o gratuito) que vaya a transferir mediante una Carta de autorización (LOA, Letter of Authorization). En la Carta de autorización (LOA), debe seleccionar el tipo correcto del número de servicio. Al ponerse en contacto con el soporte técnico de Microsoft, asegúrese de especificar que está transfiriendo un número de servicio (*y no un número de usuario o de suscriptor*) o su capacidad de llamadas simultáneas tal vez no sea suficiente para hacer frente a los volúmenes de llamadas. Si desea transferir los números de teléfono o hacer otras cosas con ellos, consulte [Administrar los números de teléfono de su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Paso 5: si desea configurar planes de llamadas

Si ha sido siguiendo los pasos anteriores, ya habrá comprado y asignado el sistema telefónico, las licencias y un plan de llamadas (paso 2), y adquirido números de teléfono para los usuarios (paso 3), por lo que su plan de llamadas ya estará parcialmente configurado. Siga los tres procedimientos siguientes para completar la configuración de dicho plan de llamadas.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>Agregar direcciones y ubicaciones de emergencia para su organización

1. En la página **Voz**, elija **Ubicaciones de emergencia** > **Agregar nueva dirección**.

2. En el panel **Nueva dirección**, introduzca un nombre para la dirección y, a continuación, complete los cuadros restantes.

     ![Al escribir una dirección de emergencia nueva, el formato del nombre de la calle puede provocar un error.](../images/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)

    > [!TIP]
    > Para los clientes que hablan inglés, si el nombre de la calle es un número, asegúrese de incluir "st" o "th" al final, como se muestra en la imagen anterior.

3. Elija **Validar**.

    Si es necesario, se le pedirá que realice correcciones a la dirección.

    > [!CAUTION]
    > Validar una dirección civil o postal implica asegurarse de que sea legítima y tenga el formato correcto. Es posible que una dirección de emergencia parcialmente correcta, por ejemplo con el nombre de la ciudad mal escrito, pueda seguir pasando como válida. Incluso si está mal escrita, pero pasó la validación, la combinación del nombre de la ciudad mal escrito junto con las demás partes correctas de la dirección constituye información suficiente para dirigir la llamada al centro de distribución emergencia correspondiente.

    > [!TIP]
    > Si es necesario corregir la dirección para una respuesta de emergencia, se mostrará un banner verde que le informa que la dirección se ha actualizado.

4. Tras la validación de la dirección, elija **Guardar**.

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>Asignar números de teléfono y direcciones de emergencia a los usuarios

> [!TIP]
> Si agrega más personas a la empresa justo antes de realizar este paso, es posible que demoren **varias horas** en aparecer en la página **Usuarios de voz**. Existe latencia.

1. En la página **Usuarios de voz**, elija la persona a la que quiera asignar un número de teléfono y una dirección de emergencia.

2. Elija **Asignar número**.

3. En la página **Asignar número**, en el menú desplegable **Seleccione el número que desea asignar**, seleccione el número de teléfono para el usuario.

4. Para seleccionar una dirección de emergencia, escriba el nombre de la ciudad en el cuadro **Buscar ciudad** y elija Buscar.

    > [!IMPORTANT]
    > Si se encuentra fuera de los Estados Unidos, los números ya tienen una dirección de emergencia, pero puede cambiarla ahora. Consulte [Asignar o cambiar la dirección de emergencia de un usuario](../what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user.md).

5. Después de asignar tanto el número de teléfono como la dirección de emergencia, elija **Guardar**.

### <a name="tell-your-users-about-their-new-phone-numbers"></a>Informar a los usuarios de sus números de teléfono nuevos


Recomendamos enviar un correo o usar el método de comunicación preferido de su empresa para informar a sus miembros de sus nuevos números de teléfono.

Aquí se muestra cómo pueden ver ese número de teléfono en su aplicación de **Skype for Business**:

1. Inicie sesión en Skype for Business en su escritorio.

2. Elija **Configuración** > **Herramientas** > **Opciones**.

     ![Para ver su número de teléfono, vaya a Configuración > Herramientas > Opciones.](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)

3. A continuación, elija **Teléfonos**.

    ![El usuario podrá ver su número asignado en la aplicación de Skype for Business eligiendo Configuración > Herramientas > Opciones > Teléfono.](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)

En **Microsoft Teams**, los usuarios pueden ver su número de teléfono haciendo clic en **Llamadas** en el panel de navegación izquierdo. El número de teléfono se muestra encima del teclado de marcado.

![Un usuario puede ver su número en Microsoft Teams haciendo clic en Llamadas en el panel de navegación izquierdo.](../images/teams-phone-number.png)

**Para obtener información más detallada acerca de todos los pasos necesarios para configurar un plan de llamadas, consulte [Configurar planes de llamadas](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Paso 6: si desea configurar la audioconferencia

En algunas ocasiones, habrá personas de su organización que necesiten un teléfono para llamar a una reunión. ¡Skype for Business y Microsoft Teams incluyen la característica de audioconferencia justo para ese tipo de situaciones! Una persona puede llamar a reuniones de Skype for Business o Microsoft Teams mediante un teléfono, en lugar de usando las aplicaciones de Skype for Business o Microsoft Teams en un dispositivo móvil o un PC.

Solo necesita configurar la audioconferencia para las personas que planeen programar o dirigir las reuniones. Los asistentes que se conectan por teléfono a la reunión no necesitan tener asignada ninguna licencia ni otra configuración.

Para ver las preguntas más frecuentes acerca de las audioconferencias, consulte [Preguntas frecuentes sobre audioconferencias](../audio-conferencing-in-office-365/audio-conferencing-common-questions.md).

1. Si ha comprado licencias del complemento de **audioconferencia** y licencias de créditos de comunicaciones, asígnelas también. Para ver las instrucciones, consulte [Asignar licencias de Skype for Business y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

    Decida cuál será su proveedor de audioconferencias. Un proveedor de audioconferencias proporciona un puente de audioconferencia. Este puente establece sus números de acceso telefónico, los PIN y los id. de la conferencia para las reuniones. Decida si prefiere utilizar Microsoft o un proveedor de audioconferencias de terceros:

    > [!NOTE]
    > Los usuarios de Microsoft Teams no pueden usar un proveedor de terceros.

    - **Microsoft como su proveedor de audioconferencias**: si busca la solución más sencilla, elija a Microsoft como su proveedor de audioconferencias.

    - **Un tercero como su proveedor de audioconferencias**: si se encuentra en un país donde no esté disponible la audioconferencia en Office 365 o en que la calidad de servicio no sea excelente debido a su ubicación, o si tiene un contrato existente, elija un proveedor de audioconferencias de terceros. Para encontrar un proveedor, vaya a [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530).

2.  Asignar el proveedor de audioconferencias a personas que dirigen o programan las reuniones. Consulte [Asignar a Microsoft como proveedor de audioconferencias](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).

3. Configurar las invitaciones a las reuniones. Los siguientes pasos son opcionales, pero hay muchos administradores a los que les gusta seguirlos:

    1. [Personalizar las invitaciones a las reuniones](../set-up-skype-for-business-online/customize-meeting-invitations.md). Los números de acceso telefónico configurados para el usuario se agregarán automáticamente a las invitaciones de las reuniones que se envíen a los asistentes. Sin embargo, puede agregar sus propios vínculos de ayuda y de avisos legales, un mensaje de texto y un pequeño distintivo gráfico de la empresa.

    2. [Establecer los números de teléfono de audioconferencia para los organizadores de la reunión que se incluyen en las invitaciones](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md). Ese es el número de teléfono que aparecerá en la reunión programada por el usuario.

    3. [Establecer el idioma del operador automático para audioconferencias](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que ese operador usará para saludar al autor de la llamada cuando este se conecte a un número de teléfono de la audioconferencia. Este paso solo se aplica si está utilizando Microsoft como su proveedor de audioconferencias.

    4. [Establecer la longitud del PIN para las reuniones mediante audioconferencia](../audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings.md).

    > [!NOTE]
    > Esta característica aún no está disponible para los clientes con Office 365 operado por 21Vianet en China. Para más detalles, consulte [Obtener información acerca de Office 365 operado por 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).

**Para obtener más información acerca de las audioconferencias, consulte [Configurar las audioconferencias](../audio-conferencing-in-office-365/set-up-audio-conferencing.md).**

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a>Paso 7: si desea configurar una cola de llamadas del sistema telefónico

Las colas de llamadas del sistema telefónico incluyen el saludo que se usa cuando alguien llama a un número de teléfono de su organización, la capacidad de poner llamadas en espera y la de localizar a un agente disponible para responder a la llamada mientras quien llama escucha una música durante la espera. Puede crear una o varias colas de llamadas para su organización.

Antes de crear o configurar una cola, tendrá que obtener sus números de servicio de pago o gratuitos, o transferir unos existentes. Después de obtener los números de teléfono de servicio de pago o gratuitos, se mostrarán en **Centro de administración de Skype for Business** > **Voz** > **Números de teléfono**, y el **Tipo de número** listado aparecerá como **Servicio - gratuito**. Para obtener sus números de servicio, consulte [Obtener números de teléfono de servicio para Skype for Business y Microsoft Teams](getting-service-phone-numbers.md) o, si desea transferir un número de servicio existente, consulte [Transferir números de teléfono a Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).

> [!NOTE]
> Si se encuentra fuera de Estados Unidos, no podrá usar el centro de administración de Skype for Business para obtener los números de servicio. En ese caso, consulte en cambio [Administrar números de teléfono para su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para ver cómo hacerlo desde fuera de Estados Unidos.

Para crear una nueva cola de llamadas, en el **Centro de administración de Skype for Business**, haga clic en **Enrutamiento de llamadas** > **Colas de llamadas**, luego haga clic en **Agregar nuevo** y a continuación siga las instrucciones que aparecen en el **Paso 3** de [Crear una cola de llamadas del sistema telefónico]( create-a-phone-system-call-queue.md#step-3---create-a-new-call-queue).

**Para obtener más información acerca de las colas, consulte [Crear una cola de llamadas del sistema telefónico](create-a-phone-system-call-queue.md).**

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a>Paso 8: si desea configurar un operador automático del sistema telefónico

Los operadores automáticos permiten que las personas que llaman a su organización naveguen por un sistema de menús para acceder al departamento correcto, a una cola de llamadas, una persona o un operador. Puede crear un operador automático para su organización usando el centro de administración de Skype for Business.

Para crear un nuevo operador automático, en el centro de administración de Skype for Business, haga clic en **Enrutamiento de llamadas** > **Operadores automáticos**, y luego haga clic en **Agregar nuevo** y a continuación siga las instrucciones para cada página en el **Paso 2** de [Configurar un operador automático del sistema telefónico](set-up-a-phone-system-auto-attendant.md#step-2---create-a-new-auto-attendant).

**Para obtener más información sobre los operadores automáticos, consulte [Configurar un operador automático del sistema telefónico](set-up-a-phone-system-auto-attendant.md).**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Paso 9: asignar los números de teléfono de servicio (audioconferencia, colas de llamadas, operadores automáticos)

Una vez que obtenga sus números de servicio mediante el **Paso 4 de arriba**, debe asignarlos a cada tipo de servicio que desee. Por ejemplo, si pretende tener un número de teléfono de servicio dedicado (de pago o gratuito), debe asignar el número al puente de conferencia.

- Para audioconferencias, puede asignar un número dedicado a un puente de conferencias yendo al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Audioconferencias** y haciendo clic en el puente de conferencia, o consultando [Cambiar los números de teléfono de pago o gratuitos en su puente de audioconferencias](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- Para los operadores automáticos, puede asignar un número dedicado a un operador automático yendo al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Enrutamiento de llamadas** > **Operadores automáticos** y haciendo clic en el operador automático. En la página **General**, el número de servicio que ya tenga aparecerá en la lista desplegable **Número de teléfono**. Para obtener información detallada, consulte [Configurar un operador automático del sistema telefónico](set-up-a-phone-system-auto-attendant.md).

- En el caso de las colas de llamadas, puede asignar un número dedicado a una de ellas yendo al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Enrutamiento de llamadas** > **Colas de llamadas** y haciendo clic en la cola de llamadas. En la página **General**, el número de servicio que ya tenga aparecerá en la lista desplegable **Número de teléfono**. Para obtener información detallada, consulte [Crear una cola de llamadas del sistema telefónico](create-a-phone-system-call-queue.md).

**Para ver información detallada sobre cómo obtener nuevos números de servicio y hacer la portabilidad de otros ya existentes, consulte [Obtener números de teléfono de servicio](getting-service-phone-numbers.md).**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Paso 10: configurar créditos de comunicaciones para su organización

Debe configurar créditos de comunicaciones si pretende usar números gratuitos con Skype for Business y Microsoft Teams. Además, es recomendable configurar créditos de comunicaciones para sus planes de llamadas (nacionales o internacionales) y para usuarios de audioconferencias que necesiten poder llamar a números de **cualquier destino**. Se incluyen muchos países y regiones, pero algunos destinos pueden no figurar en sus suscripciones del plan de llamadas o de audioconferencias. Si no ha configurado la facturación de créditos de comunicaciones y asignado una licencia de **créditos de comunicaciones** a los usuarios y se queda sin minutos disponibles para su organización (conforme al plan de llamadas o de audioconferencias de su país o región), esos usuarios no podrán realizar llamadas o marcar números de las reuniones de audioconferencia. Puede obtener más información, incluida la cantidad de fondos que se recomienda, consultando [¿Qué son los créditos de comunicaciones?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)

> [!NOTE]
> Para saber cuánto cuesta, [consulte aquí las tarifas](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).

### <a name="to-set-up-communications-credits"></a>Configurar créditos de comunicaciones

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. En el panel de navegación izquierdo del centro de administración de Office 365, vaya a **Facturación** > **Suscripciones** > **Complementos** > **Comprar complementos**, y a continuación elija **Créditos de comunicaciones** > **Comprar ahora**.

3. En la página de suscripción de los **Créditos de comunicaciones**, rellene la información y después haga clic en **Siguiente**.

4. Escriba la información de pago y haga clic en **Realizar pedido**.
    >[!IMPORTANT]
    >Si es un cliente de licencias por volumen, puede elegir su número de enterprise agreement para el pago. Si tiene varios números, podrá seleccionar qué enterprise agreement prefiere usar para dicho pago. También podrá especificar un número de pedido de compra que asociar al número del enterprise agreement (si procede).

**Para obtener información más detallada acerca de cómo configurar créditos de comunicaciones, consulte [Configurar créditos de comunicaciones para su organización](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).**

### <a name="assign-a-communications-credits-license-to-users"></a>Asignar una licencia de créditos de comunicaciones a los usuarios

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. En el panel de navegación izquierdo del centro de administración de Office 365, vaya a **Usuarios** > **Usuarios activos** y después seleccione en la lista el usuario o usuarios que correspondan.

3. En el panel de acciones bajo **Licencias de productos**, haga clic en **Editar**.

4. En la página **Licencias de productos**, establezca la alternancia de **Créditos de comunicaciones** en **On** para asignar esta licencia, y a continuación haga clic en **Guardar**.

    > [!NOTE]
    > Es recomendable que lo haga aunque tenga usuarios que estén asignados a una licencia **Enterprise E5**.

**Para obtener más información acerca de la asignación de licencias de créditos de comunicaciones, consulte [Configurar créditos de comunicaciones para su organización](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).**

## <a name="related-topics"></a>Temas relacionados
[Esto es lo que conseguirá con el sistema telefónico de Office 365](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio para Skype for Business y Microsoft Teams](getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)


