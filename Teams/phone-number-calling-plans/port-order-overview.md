---
title: ¿Qué es un pedido de portabilidad?
ms.author: v-lanac
author: lanachin
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
description: Obtenga información general sobre qué son los pedidos de los puertos y cómo transferir números de teléfono de su proveedor de servicios a teams.
ms.openlocfilehash: ecc14566573cf90d24323e65491851be86252b1a
ms.sourcegitcommit: 6f89b1ed41e437030167d104c08335445f013b32
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "47399525"
---
# <a name="whats-a-port-order"></a>¿Qué es un pedido de portabilidad?

Si actualmente tiene un proveedor u operador de servicios telefónico y ya tiene números de teléfono para sus usuarios o servicios, debe crear un "*pedido de portabilidad*" para transferir esos números de teléfono a Microsoft Teams. Cuando se transportan los números, puede asignarlos a sus usuarios y servicios, como audioconferencias (para puentes en conferencia), operadores automáticos y colas de llamadas.
  
Después de trasladar los números de teléfono a Teams, Microsoft se convierte en el proveedor de servicios y puede desconectar el servicio con su antiguo proveedor de servicios u operador.

Revise la información de este artículo para familiarizarse con la portabilidad de números. Después de ese, debe estar listo para crear una solicitud de portabilidad y transferir los números de teléfono. Consulte [transferir números de teléfono a teams](transfer-phone-numbers-to-teams.md) para obtener instrucciones paso a paso.
  
## <a name="what-countries-or-regions-support-number-porting"></a>¿Qué países o regiones son compatibles con la portabilidad de números?

Puede trasladar o transferir números de teléfono en todos los países o regiones admitidos, pero la forma en que envía una solicitud de portabilidad depende del país o de la región de donde provienen los números de teléfono. Para obtener una lista de países y regiones que admitan portabilidad de números, consulte [administrar números de teléfono de su organización](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).  

En la actualidad, [el Asistente para la migración](transfer-phone-numbers-to-teams.md) del centro de administración de Microsoft Teams admite la obtención de números de teléfono para el Reino Unido, Estados Unidos y Canadá. Para obtener números de teléfono para otros países y regiones, puede [enviar manualmente una solicitud de portabilidad](manually-submit-port-order.md).
  
## <a name="what-numbers-can-be-transferred"></a>¿Qué números se pueden transferir?

 **Puedes transferir**
  
En general, puede transferir cualquier número de teléfono que sea de un proveedor admitido, entre los que se incluyen:
  
- Números de teléfono de líneas fijas.

- Números de teléfono de dispositivos móviles, como los que se usan para el teléfono móvil y las tabletas.

    > [!NOTE]
    > La transferencia de números de teléfono móvil solo está disponible en Estados Unidos y Puerto Rico.
  
- Números de teléfono de pago.

- Números de teléfono gratuitos

    > [!NOTE]
    > El número de teléfono internacional Internacional (UIFN) no puede transferirse a nosotros. 
  
- Números de teléfono de servicios, como los usados para puentes de conferencia, operadores automáticos, etc.

- Números de teléfono de fax, pero no se pueden usar para fax. Deben asignarse a un usuario.

- Números de teléfono VoIP de un proveedor de telefonía como Vonage o RingCentral.

- Números de teléfono híbridos de Skype empresarial. Si deseas transferir estos números, envíanos un mensaje de correo electrónico a <ptn@microsoft.com> .

  **No puede transferir:**
  
    > [!NOTE]
    > En este momento, no puedes transferir ningún número de teléfono o números que no sean de un país o una región admitidos, incluidos los números de teléfono de un proveedor de telefonía VoIP. Para obtener una lista de los países o regiones admitidos, consulta [disponibilidad de países y regiones para las conferencias de audio y los planes de llamadas](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Números de teléfono usados para conexiones de datos, como números para líneas ADSL o conexiones a Internet de banda ancha.

- Los números de teléfono dedicados para fax.

    Si ya tiene números de teléfono dedicados que se usan para el envío de faxes,  *puede*  transferir estos números a Teams, pero los servicios de fax no seguirán funcionando de la forma esperada. Los servicios de fax no están disponibles para los clientes de los equipos, incluso si tiene licencias para el sistema telefónico, un plan de llamadas nacionales o un plan de llamadas internacionales.

    Si traslada el número de teléfono a Teams, puede asignar este número de teléfono a un usuario de su organización en lugar de usarlo para el envío de faxes.

    > [!NOTE]
    > En este momento, en el Reino Unido, no admitimos la transferencia de números no geográficos del Reino Unido, incluidos los números de costo compartido para códigos de área 0843, 0844, 0845, 0870, 0871, 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>¿Qué información debo proporcionar?

Debes tener toda la información de la cuenta de tu operador actual. La información que escriba en el orden de los puertos se encuentra principalmente en la factura o factura más reciente de su proveedor de servicios actual. También necesita saber cuyo nombre está en la cuenta y qué números desea portar.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>¿Qué son las transferencias de portabilidad completa y portabilidad parcial?

Cuando transporta números de teléfono a Teams, tiene la opción de transferir todos sus números o algunos de ellos.
  
- **Puerto completo** Este es el momento en que se transfieren todos los números de su proveedor de servicios actual a teams. Cuando se le pidan los números de teléfono que desea transferir, *debe incluir* el número de teléfono de facturación (BTN) junto con todos los demás números de teléfono de su cuenta.

    Por ejemplo, supongamos que BTN es  *+ 1 425-555-1234*  y deseas migrar todos tus números de 25 números de teléfono (*+ 1 425-555-1235 a 1259*). Cuando sigas las instrucciones a continuación para transferir tus números, escribiría: **+ 14255551234-+ 14255551259**.

- **Puerto parcial** Esto es cuando solo está transfiriendo algunos de los números de teléfono de su proveedor de servicios actual a teams. Cuando desees migrar algunos de los números de teléfono relacionados con el mismo BTN, * * *no debe incluir* * * el BTN junto con todos los demás números de teléfono de tu cuenta.

    Por ejemplo, supongamos que BTN es  *+ 1 425-555-1234*  y solo quiere usar un puerto de 5 de sus 25 números de teléfono (*+ 1 425-555-1235 a 1259*). Cuando sigas las instrucciones a continuación para transferir tus números, escribiría: **+ 1 425 555 1235-+ 1 425 555 1239**.
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>¿Puedo enviar una sola solicitud de portabilidad de número para todos mis números a la vez?
<a name="bkmk_type_1"> </a>

Se requiere una solicitud separada para cada operador y tipo de número cuya portabilidad se desea solicitar.
  
Por ejemplo, debe enviar una solicitud separada de portabilidad de número para cada uno de los siguientes tipos y números:
  
- Números de teléfono locales, también conocidos como números de abonados o números geográficos

- Números gratuitos con códigos de área como: 800, 844, 855, 866, 877 y 888

- Números de teléfono móvil

- Números de servicio que se pueden usar para conferencias de audio en Microsoft 365 u Office 365.

Aquí tiene más información sobre cómo enviar solicitudes de portabilidad de números para cada uno de estos tipos de números:
  
- **Los números de teléfono** proporcionados por diferentes operadores requieren una solicitud de portabilidad única para números con cada operador.

- **Los números** gratuitos con códigos de área como: 800, 844, 855, 866, 877 y 888 no se pueden incluir en una solicitud de portabilidad de número con otros tipos de números. Para trasladar estos números gratuitos, debes [enviar manualmente una solicitud de portabilidad](manually-submit-port-order.md). No puede portar estos números en el centro de administración de Microsoft Teams. Para obtener más información, consulte [Administrar los números de teléfono para su organización](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    Es importante que use la letra de autorización (LOA) correcta para el país y el tipo de números de teléfono que desea portar. Puede [descargar la loa que necesita aquí](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Los **números de teléfono móvil** requieren un código PIN para autorizar la transferencia. Por lo tanto, requieren solicitudes de portabilidad de número separadas.

- Las solicitudes de portabilidad de **números de servicio** se deben enviar por separado. No se pueden enviar con otros tipos de números.

## <a name="how-long-does-it-take-to-port-numbers"></a>¿Cuánto tiempo se tarda en realizar la portabilidad de los números?
<a name="bkmk_type_1"> </a>

Una vez completada la solicitud de solicitud de portabilidad, tarda entre 7-14 días en procesarse. Sin embargo, según su proveedor de servicios, podría tardar hasta 30 días. Una vez que se transportan los números de teléfono, recibirás un mensaje de correo electrónico de nosotros para que estés listo.
  
Para comprobar el estado de la solicitud de portabilidad, en el navegación izquierdo del centro de administración de Microsoft Teams, vaya a números de teléfono de **voz**  >  **Phone numbers**y, a continuación, haga clic en **historial de pedidos**. Cada estado de pedido de puerto se muestra en la columna **Estado** .
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>¿Es posible convertir los números de teléfono de usuario (suscriptor) en números de servicio?
<a name="bkmk_type_1"> </a>

Sí, lo es. Solo necesita enviar una solicitud de servicio que incluya el GUID del inquilino de su organización y los números de teléfono que desea convertir. Para ello, consulte [administrar números de teléfono de su organización](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>¿Puedo transferir mis números de Teams a un proveedor u operador de servicios telefónicos diferente?

Para migrar sus números de Teams a un operador diferente, debe enviar una solicitud con el nuevo operador. También necesitará establecer un PIN de migración en el centro de administración de Microsoft Teams.

Para definir el PIN de migración, en el navegación izquierdo del centro de administración de Microsoft Teams, vaya a números de teléfono de **voz**  >  **Phone numbers**, en la esquina superior derecha de la página, seleccione **administrar PIN de migración**y, a continuación, escriba un PIN de 10 dígitos.

Cuando su nuevo operador se ponga en contacto con nosotros con la solicitud de portabilidad, le pediremos que proporcione el PIN que ha definido.

## <a name="common-mistakes-to-watch-out-for"></a>Errores comunes que se deben evitar
<a name="bkmk_type_1"> </a>

El proceso de portabilidad de números es muy sencillo. Su pedido puede estar desordenado, pero si hay un problema con el proveedor de servicios telefónicos, el orden está incompleto y falta información o hay errores tipográficos.
  
A continuación se muestran los errores más comunes entre los clientes que han realizado la portabilidad de sus números. Evite tener que realizar una llamada a la asistencia al cliente y compruebe esos errores.
  
- Compruebe que la información de la cuenta que proporcione coincida exactamente con la información registrada por su operador de telefonía. Los errores de coincidencia de información son la causa más común de errores y retrasos en las solicitudes de portabilidad. Compruebe lo siguiente:

  - El nombre o la persona con autorización para realizar cambios en la cuenta son correctos.

  - La dirección es correcta.

  - El número de cuenta es correcto.

  - BTN es el correcto.

- Asegúrese de que no hay características avanzadas de control de llamadas, por ejemplo, búsqueda de llamadas, timbre distintivo, que están habilitadas en estos números de teléfono.

- Asegúrese de que no ha realizado una nueva solicitud de servicio o desconexión con su proveedor de servicios actual.

- Compruebe que todos los números sean del mismo operador y de la misma cuenta.

- No bloquee su cuenta con su proveedor de servicios. Si bloquea la cuenta, no podrá realizar el cambio de operadores en la cuenta. La persona autorizada para realizar cambios en la cuenta debe enviar un pedido al operador actual para quitar la inmovilización. Este proceso puede demorar una o tres semanas dependiendo del transportista.

## <a name="related-topics"></a>Temas relacionados

- [¿Cuál es el estado de mis solicitudes de portabilidad?](port-order-status.md)
- [Diferentes tipos de números de teléfono que se usan para Planes de llamada](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Administrar los números de teléfono para su organización](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Términos y condiciones de las llamadas de emergencia](../emergency-calling-terms-and-conditions.md)
- [Etiqueta de renuncia para llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)