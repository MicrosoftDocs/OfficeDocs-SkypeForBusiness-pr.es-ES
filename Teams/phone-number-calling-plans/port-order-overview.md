---
title: ¿Qué es un pedido de portabilidad?
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: Obtenga información general sobre qué son los pedidos de portabilidad y cómo transferir números de teléfono de su proveedor de servicios a Teams.
ms.openlocfilehash: bb9ebd91b1f5a08fb07eff0f469be4496714ecfc
ms.sourcegitcommit: 766199440a152d97c95c2c45b7c4654815e64d9a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "62963421"
---
# <a name="whats-a-port-order"></a>¿Qué es un pedido de portabilidad?

Si actualmente tiene un proveedor u operador de servicios de telefonía y ya tiene números de teléfono para sus usuarios o servicios, debe crear una "*solicitud de portabilidad*" para transferir esos números de teléfono a Microsoft Teams. Cuando se transfieren los números, puede asignar esos números de teléfono a los usuarios y servicios, como las audioconferencias (para puentes de conferencia), los operadores automáticos y las colas de llamadas.
  
Después de portar los números de teléfono a Teams, Microsoft se convertirá en su proveedor de servicios y podrá desconectar el servicio con su proveedor de servicios u operador anterior.

Revise la información de este artículo para familiarizarse con la portabilidad de números. Después de eso, podrá crear una solicitud de portabilidad y transferir los números de teléfono. Consulte [Transferir números de teléfono a Teams](transfer-phone-numbers-to-teams.md) para obtener instrucciones paso a paso.
  
## <a name="what-countries-or-regions-support-number-porting"></a>¿Qué países o regiones admiten la portabilidad de números?

Puede portar o transferir números de teléfono en todos los países y regiones permitidos, pero la manera de enviar una solicitud de portabilidad dependerá del país o región al que pertenezca ese número. Para obtener una lista de países y regiones que admiten la portabilidad de números, consulte [Administrar números de teléfono de su organización](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).  

Actualmente, [el asistente de portabilidad](transfer-phone-numbers-to-teams.md) en el Centro de administración de Microsoft Teams admite la obtención de números de teléfono del Reino Unido, Estados Unidos y Canadá. Para obtener números de teléfono de otros países y regiones, puede [enviar manualmente una solicitud de portabilidad](manually-submit-port-order.md).
  
## <a name="what-numbers-can-be-transferred"></a>¿Qué números se pueden transferir?

 **Puede transferir**
  
En general, puede transferir cualquier número de teléfono de un proveedor admitido, incluidos:
  
- Números de teléfono de líneas fijas.

- Números de teléfono de dispositivos móviles, como los que se usan para teléfonos móviles y tabletas.

    > [!NOTE]
    > La transferencia de números móviles solo está disponible en los Estados Unidos y Puerto Rico.
  
- Números de teléfono de pago.

- Números de teléfono gratuitos

    > [!NOTE]
    > El número universal internacional de llamada gratuita (UIFN) no se puede transferir a nosotros. 
  
- Números de teléfono de servicios, como los usados para puentes de conferencia, operadores automáticos, etc.

- Números de teléfono de fax, pero no se pueden usar para fax. Deben asignarse a un usuario.

- Números de teléfono VoIP de un proveedor de telefonía como Vonage o RingCentral.

- Números de teléfono híbridos de Skype Empresarial. Si desea transferir estos números, envíenos un correo electrónico a <ptn@microsoft.com>.

**No puede transferir:**
  
> [!NOTE]
> En este momento, no puede transferir ningún número de teléfono o números que no sean de uno de los países o regiones admitidos, incluidos los números de teléfono de un proveedor de teléfono VoIP. Para obtener una lista de los países o las regiones admitidos, vea [Países y regiones donde Audioconferencia y Planes de llamada estén disponibles](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- Números de teléfono usados para conexiones de datos, como números para líneas ADSL o conexiones a Internet de banda ancha.

- Los números de teléfono dedicados para fax.

    Si tiene números de teléfono dedicados existentes que se usan para enviar fax, *puede* transferir estos números a Teams, pero los servicios de fax no seguirán funcionando como se espera. Los servicios de fax no están disponibles para los clientes de Teams, incluso si tiene licencias para Sistema telefónico, el plan de llamadas nacionales o el plan de llamadas internacionales.

    Si porta el número de teléfono a Teams, puede asignar este número de teléfono a un usuario de su organización, en lugar de usarlo para enviar fax.

> [!NOTE]
> En este momento en el Reino Unido, no se admite la transferencia de números no geográficos del Reino Unido, incluidos los números de costo compartido para los códigos de área 0843, 0844, 0845, 0870, 0871, 0872.
  
## <a name="what-information-do-i-need-to-provide"></a>¿Qué información necesito proporcionar?

Debe tener toda la información de la cuenta para su operador actual. La información que especifique en la solicitud de portabilidad se encuentra principalmente en la factura más reciente de su proveedor de servicios actual. También debe saber a nombre de quién está la cuenta y los números que quiere portar.
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>¿Qué son las transferencias de portabilidad completa y portabilidad parcial?

Al portar números de teléfono a Teams, tiene la opción de transferir todos los números o algunos de ellos.
  
- **Portabilidad completa** Es cuando se transfieren todos los números de su proveedor de servicios actual a Teams. Cuando se le pidan los números de teléfono que desea transferir, *debe incluir* el número de teléfono de facturación (BTN) junto con los demás números de teléfono de su cuenta.

    Por ejemplo, si el número de teléfono de facturación es  *+1 425-555-1234*  y quiere realizar la portabilidad de todos los 25 números de teléfono (*desde +1 425-555-1235 hasta 1259*), cuando siga las instrucciones siguientes para transferir sus números, escribiría: **+14255551234 - +14255551259**.

- **Portabilidad parcial** Es cuando se transfieren algunos de los números de teléfono de su proveedor de servicios actual a Teams. Cuando quiere portar algunos de los números de teléfono asociados al mismo BTN, ** *no debe incluir* ** el BTN junto con los demás números de teléfono de su cuenta.

    Por ejemplo, si el número de teléfono de facturación (BTN) es  *+1 425-555-1234*  y solo quiere transferir 5 de sus 25 números de teléfono (*del +1 425-555-1235 al 1259*), solo tendría que escribir lo siguiente si sigue las instrucciones para transferir sus números: **+1 425 555 1235 - +1 425 555 1239**
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>¿Puedo enviar una sola solicitud de portabilidad de número para todos mis números a la vez?
<a name="bkmk_type_1"> </a>

Se requiere una solicitud separada para cada operador y tipo de número cuya portabilidad se desea solicitar.
  
Por ejemplo, debe enviar una solicitud separada de portabilidad de número para cada uno de los siguientes tipos y números:
  
- Números de pago locales, también conocidos como números de suscriptor o números geográficos.

- Números gratuitos con códigos de área como: 800, 844, 855, 866, 877 y 888

- Números de teléfono móvil

- Números de servicio que pueden usarse para audioconferencias en Microsoft 365 u Office 365.

Aquí tiene más información sobre cómo enviar solicitudes de portabilidad de número para cada uno de estos tipos de números:
  
- Los **números de teléfono** proporcionados por diferentes operadores requieren una solicitud única de portabilidad para los número con cada operador.

- Los **números gratuitos** con códigos de área como 800, 844, 855, 866, 877 y 888 no se pueden incluir en una solicitud de portabilidad de número con otros tipos de números. Para portar estos números gratuitos, debe [enviar manualmente una solicitud de portabilidad](manually-submit-port-order.md). No puede portar estos números en el Centro de administración de Microsoft Teams. Para obtener más información, consulte [Administrar los números de teléfono para su organización](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    Es importante usar la carta de autorización correcta para el país y el tipo de números de teléfono que quiere portar. Aquí puede [descargar la carta de autorización que necesita](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Los **números de teléfono móvil** requieren un código PIN para autorizar la transferencia. Por lo tanto, requieren solicitudes de portabilidad de número separadas.

- Las solicitudes de portabilidad de **números de servicio** se deben enviar por separado. No se pueden enviar junto con otros tipos de números.

## <a name="how-long-does-it-take-to-port-numbers"></a>¿Cuánto tiempo se tarda en realizar la portabilidad de los números?
<a name="bkmk_type_1"> </a>

Una vez completada la solicitud de portabilidad, el proceso tarda entre 7 y 14 días. Sin embargo, en función de su proveedor de servicios, pueden tardar hasta 30 días. Después de portar los números de teléfono, recibirá un correo electrónico de nosotros para informarle de que ya está listo.
  
Para comprobar el estado de la solicitud de portabilidad, en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Voz** > **Números de teléfono** y, después, haga clic en **Historial de solicitudes**. El estado de cada solicitud de portabilidad se muestra en la columna **Estado**.
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>¿Es posible convertir los números de teléfono de usuario (suscriptor) en números de servicio?
<a name="bkmk_type_1"> </a>

Sí, lo es. Solo necesita enviar una solicitud de servicio que incluya el GUID del inquilino de su organización y los números de teléfono que desea convertir. Puede hacerlo en [Administrar los números de teléfono de su organización](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>¿Puedo portar mis números de Teams a un proveedor de servicios de telefonía o un operador distintos?

Para portar los números de Teams a un operador diferente, debe enviar una solicitud con el nuevo operador. También debe establecer un PIN de portabilidad en el Centro de administración de Microsoft Teams.

Para definir el PIN de portabilidad, en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Voz** > **Números de teléfono** y, en la esquina superior derecha de la página, seleccione **Administrar PIN de portabilidad** y escriba un PIN de 10 dígitos.

Cuando el nuevo operador se ponga en contacto con nosotros con la solicitud de portabilidad, le pediremos que proporcione el PIN que ha definido.

Si necesita seguir configurando un PIN, póngase en contacto con el [equipo de servicios de números de teléfono](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)

## <a name="common-mistakes-to-watch-out-for"></a>Errores comunes que se deben evitar
<a name="bkmk_type_1"> </a>

La portabilidad de número es fácil de realizar. Sin embargo, su solicitud se puede complicar si hay un problema con el proveedor de servicios de telefonía, la solicitud está incompleta y falta información o hay errores tipográficos.
  
A continuación se muestran los errores más comunes entre los clientes que han realizado la portabilidad de sus números. Evite tener que realizar una llamada a la asistencia al cliente y compruebe esos errores.
  
- Compruebe que la información de la cuenta que proporcione coincida exactamente con la información registrada por su operador de telefonía. Los errores de coincidencia de información son la causa más común de errores y retrasos en las solicitudes de portabilidad. Compruebe lo siguiente:

  - El nombre o la persona autorizada para realizar cambios en la cuenta es correcto.

  - La dirección es correcta.

  - El número de cuenta es correcto.

  - El BTN es correcto.

- Asegúrese de que no existen características avanzadas de control de llamadas, por ejemplo, Búsqueda de llamadas o Tono distintivo, que están habilitadas en estos números de teléfono.

- Asegúrese de que no ha realizado una nueva solicitud de servicio o desconexión con su proveedor de servicios actual.

- Compruebe que todos los números sean del mismo operador y de la misma cuenta.

- Asegúrese de que el servicio está activo. La inmovilización de la cuenta impide el cambio de operadores en la cuenta. La persona autorizada para realizar cambios en la cuenta debe enviar una solicitud al operador actual para quitar la inmovilización. Este proceso puede tardar entre una y tres semanas, según el operador.

## <a name="related-topics"></a>Temas relacionados

- [¿Cuál es el estado de mis solicitudes de portabilidad?](port-order-status.md)
- [Diferentes tipos de números de teléfono que se usan para Planes de llamada](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Administrar los números de teléfono para su organización](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Términos y condiciones de las llamadas de emergencia](../emergency-calling-terms-and-conditions.md)
- [Etiqueta de declinación de responsabilidades de llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
