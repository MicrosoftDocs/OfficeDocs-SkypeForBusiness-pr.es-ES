---
title: ¿Qué es un pedido de portabilidad?
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: Obtenga información general sobre qué son las órdenes de portabilidad y cómo transferir números de teléfono de su proveedor de servicios a Teams.
ms.openlocfilehash: 4f1f8ca843db8c2b27eaa467b0014befe6f2b519
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802510"
---
# <a name="whats-a-port-order"></a>¿Qué es un pedido de portabilidad?

Si actualmente tiene un proveedor de servicios u operador de telefonía y ya tiene números de teléfono para sus usuarios o servicios, debe crear una *"orden* de portabilidad" para transferir esos números de teléfono a Microsoft Teams. Cuando los números se asignen, podrá asignarlos a los usuarios y servicios como audioconferencia (para puentes de conferencia), operadores automáticos y colas de llamadas.
  
Después de realizar la portabilidad de sus números de teléfono a Teams, Microsoft se convierte en su proveedor de servicios y puede desconectar el servicio con su proveedor de servicios u operador anterior.

Revise la información de este artículo para familiarizarse con la porización de números. Una vez hecho esto, debería estar preparado para crear una orden de portabilidad y transferir sus números de teléfono. Vea [Transferir números de teléfono a Teams](transfer-phone-numbers-to-teams.md) para obtener instrucciones detalladas.
  
## <a name="what-countries-or-regions-support-number-porting"></a>¿Qué países o regiones admiten la portención de números?

Puede portabilidad o transferir números de teléfono en todos los países o regiones admitidos, pero la forma de enviar una solicitud de portabilidad dependerá del país o la región de donde proceden los números de teléfono. Para obtener una lista de países y regiones que admiten la portención de números, vea Administrar [números de teléfono para su organización.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)  

Actualmente, [el asistente para porte](transfer-phone-numbers-to-teams.md) en el Centro de administración de Microsoft Teams admite la obtención de números de teléfono para Reino Unido, Estados Unidos y Canadá. Para obtener números de teléfono para otros países y regiones, puede enviar [manualmente una solicitud de portabilidad.](manually-submit-port-order.md)
  
## <a name="what-numbers-can-be-transferred"></a>¿Qué números se pueden transferir?

 **Puede transferir**
  
En general, puede transferir cualquier número de teléfono de un proveedor compatible, incluidos:
  
- Números de teléfono de líneas fijas.

- Números de teléfono del dispositivo móvil, como los que se usan para teléfonos móviles y tabletas.

    > [!NOTE]
    > Solo es posible transferir números de teléfono móvil en Estados Unidos y Puerto Rico.
  
- Números de teléfono de pago.

- Números de teléfono gratuitos

    > [!NOTE]
    > No se nos puede transferir el número de teléfono gratuito internacional (UIFN). 
  
- Números de teléfono de servicios, como los usados para puentes de conferencia, operadores automáticos, etc.

- Números de teléfono de fax, pero no se pueden usar para fax. Tienen que asignarse a un usuario.

- Números de teléfono VoIP de un proveedor de telefonía como Vonage o RingCentral.

- Números de teléfono híbridos de Skype Empresarial. Si desea transferir estos números, envíenos un correo electrónico al <ptn@microsoft.com> .

  **No puede transferir:**
  
    > [!NOTE]
    > Actualmente no se pueden transferir números de teléfono que no sean de un país o región admitido, incluidos los números de teléfono de un proveedor de telefonía VoIP. Para obtener una lista de los países o regiones admitidos, consulte La disponibilidad del país y la región para los planes de llamadas y [audioconferencias](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Números de teléfono usados para conexiones de datos, como números para líneas ADSL o conexiones a Internet de banda ancha.

- Los números de teléfono dedicados para fax.

    Si tiene números de teléfono dedicados existentes  que se utilizan para fax, puede transferir estos números a Teams, pero los servicios de fax no seguirán funcionando como se espera. Los servicios de fax no están disponibles para los clientes de Teams, aunque tenga licencias de Sistema telefónico, Plan de llamadas nacionales o Plan de llamadas internacionales.

    Si portabilidad del número de teléfono a Teams, puede asignarlo a un usuario de su organización en lugar de usarlo para fax.

    > [!NOTE]
    > Actualmente, en el Reino Unido no se admite la transferencia de números no geográficos a Reino Unido, incluidos los números de costo compartido para los códigos de área 0843, 0844, 0845, 0870, 0871 y 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>¿Qué información necesito proporcionar?

Debe tener toda la información de la cuenta de su operador actual. La información que introduzca en la orden de portabilidad se encuentra principalmente en la factura más reciente de su proveedor de servicios actual. También necesita saber el nombre del usuario de la cuenta y los números que desea realizar la portabilidad.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>¿Qué son las transferencias de portabilidad completa y portabilidad parcial?

Al transferir números de teléfono a Teams, tiene la opción de transferir todos sus números o solo algunos.
  
- **Puerto completo** Es cuando transfiere todos los números de su proveedor de servicios actual a Teams. Cuando se le pidan los números de  teléfono que desea transferir, debe incluir el número de teléfono de facturación (BTN) junto con el resto de los números de teléfono de su cuenta.

    Por ejemplo, supongamos que su BTN es *+1 425-555-1234* y desea portabilidad todos sus 25 números de teléfono *(+1 425-555-1235 a 1259).* Cuando siga las instrucciones siguientes para transferir sus números, tendría que escribir: **+14255551234 - +14255551259**.

- **Portabilidad parcial** En este caso, solo va a transferir algunos de sus números de teléfono desde su proveedor de servicios actual a Teams. Para realizar la portabilidad de algunos de los números de teléfono vinculados a la misma BTN, **** no debe incluir ** el BTN junto con el resto de los números de teléfono de su cuenta.

    Por ejemplo, supongamos que su BTN es *+1 425-555-1234* y desea portabilidad solo 5 de sus 25 números de teléfono *(+1 425-555-1235 a 1259).* Cuando siga las instrucciones siguientes para transferir sus números, tendría que escribir: **+1 425 555 1235 - +1 425 555 1239.**
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>¿Puedo enviar una sola solicitud de portabilidad de número para todos mis números a la vez?
<a name="bkmk_type_1"> </a>

Se requiere una solicitud separada para cada operador y tipo de número cuya portabilidad se desea solicitar.
  
Por ejemplo, debe enviar una solicitud separada de portabilidad de número para cada uno de los siguientes tipos y números:
  
- Números de pago locales, también conocidos como números geográficos o de suscriptor

- Números gratuitos con códigos de área como: 800, 844, 855, 866, 877 y 888

- Números de teléfono móvil

- Números de servicio que se pueden usar para Audioconferencia en Microsoft 365 u Office 365.

Aquí tiene más información sobre cómo enviar solicitudes de pornografía de número para cada uno de estos tipos de números:
  
- **Los números** de teléfono proporcionados por diferentes operadores requieren una solicitud de pornografía única para los números de cada operador.

-  Los números gratuitos con códigos de área como: 800, 844, 855, 866, 877 y 888 no se pueden incluir en una solicitud de porción de número con otros tipos de números. Para realizar la portabilidad de estos números gratuitos, debe [enviar manualmente una solicitud de portabilidad.](manually-submit-port-order.md) No puede realizar la portabilidad de estos números en el Centro de administración de Microsoft Teams. Para obtener más información, consulte [Administrar los números de teléfono para su organización](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    Es importante usar la Carta de autorización (LOA) correcta para el país y el tipo de número de teléfono que desea portabilidad. Puede descargar [la LOA que necesita aquí.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Los **números de teléfono móvil** requieren un código PIN para autorizar la transferencia. Por lo tanto, requieren solicitudes de portabilidad de número separadas.

- Las solicitudes de portabilidad de **números de servicio** se deben enviar por separado. No se pueden enviar con otros tipos de números.

## <a name="how-long-does-it-take-to-port-numbers"></a>¿Cuánto tiempo se tarda en realizar la portabilidad de los números?
<a name="bkmk_type_1"> </a>

Una vez completada la solicitud de portabilidad, el proceso tarda entre 7 y 14 días. Sin embargo, según su proveedor de servicios, podría tardar hasta 30 días. Cuando se autorguen los números de teléfono, le enviaremos un correo electrónico para que pueda irte a otro lugar.
  
Para comprobar el estado de su orden de portabilidad, en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Números de teléfono de voz y haga clic en  >  Historial **de pedidos.** El estado de cada orden de portabilidad se muestra en la **columna** Estado.
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>¿Es posible convertir los números de teléfono de usuario (suscriptor) en números de servicio?
<a name="bkmk_type_1"> </a>

Sí, lo es. Solo necesita enviar una solicitud de servicio que incluya el GUID del inquilino de su organización y los números de teléfono que desea convertir. Para ello, vea Administrar [números de teléfono de su organización.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>¿Puedo realizar la portabilidad de mis números de Teams a otro proveedor de servicios u operador de telefonía?

Para realizar la portabilidad de los números de Teams a otro operador, debe enviar una solicitud al nuevo operador. También necesitará establecer un PIN de pornografía en el Centro de administración de Microsoft Teams.

Para definir el PIN de pornografía, en el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a Números de teléfono de voz, en la esquina superior derecha de la página, seleccione Administrar PIN de pornografía y, a continuación, escriba un PIN de  >  10 dígitos. 

Cuando su nuevo operador se pone en contacto con nosotros con la solicitud de porte, le solicitaremos que le proporcione el PIN que ha definido.

## <a name="common-mistakes-to-watch-out-for"></a>Errores comunes que se deben evitar
<a name="bkmk_type_1"> </a>

El proceso de portabilidad de números es muy sencillo. Sin embargo, la solicitud se puede desordenar si hay un problema con el proveedor de servicios de telefonía, la solicitud está incompleta y falta información o hay errores tipográficos.
  
A continuación se muestran los errores más comunes entre los clientes que han realizado la portabilidad de sus números. Evite tener que realizar una llamada a la asistencia al cliente y compruebe esos errores.
  
- Compruebe que la información de la cuenta que proporcione coincida exactamente con la información registrada por su operador de telefonía. Los errores de coincidencia de información son la causa más común de errores y retrasos en las solicitudes de portabilidad. Compruebe lo siguiente:

  - El nombre o la persona autorizada a realizar cambios en la cuenta es correcto.

  - La dirección es correcta.

  - El número de cuenta es correcto.

  - BTN es correcto.

- Asegúrese de que no haya características avanzadas de control de llamada (por ejemplo, búsqueda de llamadas o tono distintivo) habilitadas en estos números de teléfono.

- Asegúrese de que no ha realizado una nueva solicitud de servicio o desconexión con su proveedor de servicios actual.

- Compruebe que todos los números sean del mismo operador y de la misma cuenta.

- No bloquee su cuenta con su proveedor de servicios. Si bloquea la cuenta, no podrá realizar el cambio de operadores en la cuenta. La persona autorizada a realizar cambios en la cuenta debe enviar una solicitud al operador actual para eliminar el bloqueo. Este proceso puede tardar de una a tres semanas, según el operador.

## <a name="related-topics"></a>Temas relacionados

- [¿Cuál es el estado de mis solicitudes de portabilidad?](port-order-status.md)
- [Diferentes tipos de números de teléfono que se usan para Planes de llamada](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Administrar los números de teléfono para su organización](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Términos y condiciones de las llamadas de emergencia](../emergency-calling-terms-and-conditions.md)
- [Etiqueta de declinación de responsabilidades en llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)