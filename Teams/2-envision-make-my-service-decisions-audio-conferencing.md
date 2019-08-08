---
title: 'Tomar decisiones relacionadas con el servicio de Audioconferencia: Microsoft Teams'
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 12/28/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Obtenga más información sobre las reuniones, las licencias y la disponibilidad, la configuración del puente de conferencia, la adquisición o transferencia de números de teléfono y la elección de planes de marcado de inquilino.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0155788ef4ba99a350be0043847edd5e705b75b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240578"
---
# <a name="make-my-service-decisions"></a>Tomar mi decisión de servicio

Para planear la implementación técnica de audioconferencia, debe tomar una serie de decisiones de servicio antes de tiempo para preparar mejor a su organización y así implementar una solución que cumpla con los requisitos empresariales definidos.

## <a name="audio-conferencing-in-teams"></a>Audioconferencia en Teams

Como parte de la definición de características de audioconferencias obligatorias en Microsoft Teams, uno de los primeros pasos es evaluar el último plan público para determinar:

-   Qué características de audioconferencia en Teams se implementarán para los usuarios en el ámbito.

-   Requisitos de funcionalidad de usuario esperados para las conferencias de audio en Teams.

-   Confirmación de que las características de audioconferencia en teams que se describen en el último plan público cumplen con los requisitos de usuario, funcionalidad y ámbito, dentro de la escala de tiempo de la implementación.

> [!NOTE]
> La última guía básica de Microsoft para identificar Teams las características de audioconferencia en el ámbito de su <https://aka.ms/O365Roadmap>implementación puede encontrarse en.

## <a name="meetings-in-teams"></a>Reuniones en Teams

Teams proporciona a los usuarios la capacidad de programar y unirse a reuniones en línea con las opciones de conferencia de acceso telefónico de alta definición, voz sobre IP (VoIP) y RTC.

Las reuniones se pueden programar como reuniones privadas (solo se pueden unir partes invitadas) o reuniones de canal (abiertas para todos los usuarios que tengan acceso al canal) y los usuarios también pueden iniciar reuniones improvisadas dentro de los canales.

> [!NOTE]
> Para obtener más información sobre las características de las reuniones en Teams, consulte la [hoja de ruta de Microsoft 365](https://aka.ms/O365Roadmap).

Los participantes de la reunión pueden unirse a sus reuniones de Teams marcando los números de teléfono de los puentes de llamadas de acceso telefónico local o gratuitos a través de teléfonos fijos o móviles. Además, los usuarios pueden dejar que el servicio de audioconferencia inicie la característica "Llamarme" para que puedan participar en una reunión haciendo que el puente de conferencia llame a sus teléfonos (es útil cuando la conexión de datos no es confiable) o permite a los organizadores de reuniones invitar a la reunión a los participantes al llamar a sus teléfonos.

> [!IMPORTANT]
> Las conferencias de audio en Teams no admiten proveedores de audioconferencias de terceros (ACPs).

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>Disponibilidad de Audioconferencia

Antes de planear la implementación de audioconferencia en Teams, debe revisar la disponibilidad del servicio de audioconferencias, como se detalla en disponibilidad de los [países y las regiones para las conferencias de audio y los planes de llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> Debido a restricciones legales, para que las conferencias de audio estén disponibles para organizaciones multinacionales, el contrato para las suscripciones de Office 365 debe ser origen de países y regiones en los que el servicio de audioconferencia esté disponible comercialmente.

Después de confirmar que su organización es elegible para obtener el servicio de audioconferencia, compile la lista de ubicaciones o ubicaciones de usuarios donde implementará el servicio de audioconferencia, en función de la lista de países y regiones disponibles.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir qué ubicaciones o oficinas de usuario implementarán el servicio de audioconferencia.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente las ubicaciones de usuario o las oficinas que se habilitarán para el servicio de audioconferencia.</li></ul>|

> [!TIP]
> A continuación se muestra un ejemplo de una plantilla de lista de habilitación de sitios de audioconferencias:
> 
> |Office   |Ubicación |Servicio de conferencia RTC  |
> |---------|---------|---------|
> |One Epping Road|Australia|Audioconferencia|
> |100 Cyberport Road|RAE de Hong Kong|Conferencia RTC antigua|
> |One Marina Boulevard|Singapur|Audioconferencia|
> |32 London Bridge Street|Reino Unido|Audioconferencia|
> |39 quai du Président Roosevelt|Francia|Audioconferencia|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>Licencias para Audioconferencia

Hay una [licencia](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) de audioconferencias disponible como parte de los planes de suscripción a Office 365 E5 o como un servicio complementario para los planes de suscripción de Office 365 E1 u Office 365 E3.

> [!NOTE]
> Las conferencias RTC o de acceso telefónico local de Teams no admiten proveedores de audioconferencias de terceros (ACPs).
> <br>Si está usando la Conferencia RTC para Skype Empresarial Online, puede beneficiarse al instante de Audioconferencia en Microsoft Teams.

Para proporcionar números de teléfono con un puente de conferencia gratuito y para permitir el acceso telefónico de las conferencias a números de teléfono internacionales, debe configurar [créditos de comunicaciones](what-are-communications-credits.md) para su organización.

> [!IMPORTANT]
> Algunos países son atendidas por números de teléfono de puente de conferencia gratuitos. Para admitir el acceso telefónico en estos países, debe usar créditos de comunicaciones.

La primera consideración al implementar créditos de comunicaciones es decidir la cantidad inicial de fondos que desea comprar. Si su organización decide usar la recarga automática, debe decidir la cantidad del desencadenador (la cantidad más baja de fondos) y la cantidad de la recarga automática. Tu uso real determinará la cantidad de la recarga automática. Debes controlar el uso de tus créditos en las comunicaciones a lo largo del tiempo y ajustar el monto de la recarga según sea necesario.

Puede obtener más información sobre los créditos de las comunicaciones [aquí](what-are-communications-credits.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Si su organización aún no ha comprado las licencias de conferencia de audio necesarias, decida si va a adquirir licencias de audioconferencias recorriendo las suscripciones existentes de Office 365 o adquiriendo licencias de complemento de audioconferencia.</li><li>Decidir si se requieren créditos de comunicaciones para la implementación de audioconferencia. En tal caso, decida la cantidad inicial de fondos que se va a comprar. Cuando sea necesario, decida la cantidad para el umbral y la cantidad de autorecarga.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente los usuarios a los que se les asignarán licencias de audioconferencia.</li><li>Documentar el plan de crédito de las comunicaciones (cantidad inicial, valor de activación, cantidad de recarga automática)</li></ul>|

> [!TIP]
> Puede documentar la lista de asignación de licencias de los usuarios de la Conferencia de audio con el siguiente ejemplo.
> 
> |Usuario  |Oficina  |Licencia de Office 365  |
> |---------|---------|---------|
> |Adele Vance|One Epping Road|Office 365 E5|
> |Alex Wilber|One Epping Road|Office 365 E3, complemento de Audioconferencia|
> |Ben Walters|One Epping Road|Office 365 E3, complemento de Audioconferencia|
> |Christie Cline|One Marina Boulevard|Office 365 E3, complemento de Audioconferencia|
> |Debra Berger|One Marina Boulevard|Office 365 E5|
> |Lee Gu|One Marina Boulevard|Office 365 E5|
> |Emily Braun|32 London Bridge Street|Office 365 E5|
> |Lidia Holloway|32 London Bridge Street|Office 365 E5|
> |Louis Lahr|32 London Bridge Street|Office 365 E5|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, complemento de Audioconferencia|
> |Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
> |Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, complemento de Audioconferencia|

<br>

> [!TIP]
> Los números de planificación de Créditos de comunicaciones se pueden documentar del modo siguiente:
>
> |         |         |
> |---------|---------|
> |Cantidad inicial|1000 $|
> |Cantidad de umbral|400 $|
> |Cantidad de recarga automática|Por añadir|
> 
<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>Números de teléfono para puentes de conferencia

El servicio de Audioconferencia en Office 365 incluye:

-   Varios tipos de números de teléfono de puente de conferencia (de pago y gratuitos)

-   Varias categorías de números de teléfono de puente de conferencia (dedicados y compartidos)

-   Soporte para varios idiomas del puente de conferencia (principal y secundario)

-   Un número de teléfono predeterminado para el inquilino

> [!NOTE]
> Los números de teléfono de los puentes de conferencia dedicados se reparten hacia el límite de números de teléfono que pueden adquirirse por inquilino, en función del número de licencias vigentes. Los números de teléfono gratuitos para puentes de conferencia necesitan los Créditos de comunicaciones.

Si debe transferir los números de teléfono de puente de conferencia existentes al servicio de audioconferencia (suponiendo que cumplan con los requisitos nacionales), puede transferir estos números de teléfono de puente de conferencia existentes a Microsoft.

> [!NOTE]
> La complejidad de transferir números de teléfono a Microsoft varía en gran medida según el país o la región, el operador, el número de circuitos implicados y muchos otros factores contribuyentes. Trabaje con su proveedor actual para investigar cuánto puede tomar esto para asegurarse de que comienza el proceso lo suficientemente pronto como para cumplir con las escalas de tiempo.

Para obtener más información sobre los números de teléfono de los puentes de conferencia, consulte los artículos siguientes:

-   [Configurar audioconferencias en Microsoft Teams](set-up-audio-conferencing-in-teams.md)

-   [Números de teléfono para Audioconferencia](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [Obtener números de teléfono de servicio](getting-service-phone-numbers.md)

-   [Transferir números de teléfono a Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si su organización necesita números de teléfono de puente de conferencia dedicados.</li><li>Decidir cómo se obtendrán los números de teléfono de puente de conferencia específicos para ubicaciones de usuario o oficinas en el ámbito de la implementación de audioconferencias (es decir, obtener de Microsoft o transferir números de teléfono existentes).</li><li>Si elige obtenerlas de Microsoft, decida el método que debe usar (envío de formulario o automatizado) para las ubicaciones de usuario o las oficinas en el ámbito de la implementación de las conferencias de audio.</li><li>Decida las preferencias de idioma que desea configurar para cada número de teléfono de puente de conferencia dedicado.</li><li>Decidir el número de teléfono del puente de conferencia predeterminado del inquilino.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente el plan maestro para la adquisición de números de teléfono, detallando cómo se obtendrán los números de teléfono para cada ubicación de usuario u Office en el ámbito de la implementación de las conferencias de audio.</li><li>Si corresponde, complete el formulario de solicitud de número de teléfono nuevo: un formulario para cada ubicación u oficina.</li><li>Documente las configuraciones detalladas del número de teléfono del puente de conferencia (números de teléfono de puente de conferencia compartidos y dedicados, preferencias de idioma para cada número de teléfono de puente de conferencia dedicado, número de teléfono del puente de conferencia predeterminado).</li></ul>|

A continuación se muestra un ejemplo de una plantilla que puede usar para capturar detalles del puente de conferencia.

> [!TIP]
> A continuación se muestra un ejemplo de una plantilla para capturar los detalles de los puentes de conferencia:
> 
> |Oficina   |Adquisición de número de puente y tipo de puente |Número de puente  |Idioma de puente|
> |---------|---------|---------|---------|
> |One Epping Road|Adquirir nuevo, dedicado|Por añadir|Inglés (Australia)|
> |One Marina Boulevard|Adquirir nuevo, compartido|Por añadir|Inglés (Estados Unidos), chino (simplificado, RPC)|
> |32 London Bridge Street|Puerto existente, dedicado|+44 20 7946 0001|Inglés (Reino Unido)|
> |39 quai du Président Roosevelt|Adquirir nuevo, dedicado|Por añadir|Francés (Francia), inglés (Reino Unido)|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>Configuración de puentes de conferencia

Para personalizar aún más la experiencia del usuario, puede configurar opciones de toda la organización para unirse a reuniones de conferencia de audio (entrada y salida de reunión y grabación de nombres de llamadas), la longitud del PIN del organizador de la reunión y la notificación por correo electrónico:

-   Las notificaciones de entrada y salida de la reunión están disponibles en la forma de nombre grabado, número de teléfono y tonos.

-   La longitud del PIN se puede configurar de 4 a 12 dígitos, siendo el PIN de 5 dígitos el predeterminado.

-   Los correos electrónicos de notificación enviados por la habilitación de la licencia de audioconferencias o cualquier otro cambio controlado por el administrador están habilitados de forma predeterminada. Puede deshabilitar esta característica y tomar el control de las comunicaciones de los usuarios de su organización.

Para los usuarios a los que se les asigna una licencia de conferencias de audio, los números de pago/gratis predeterminados, que se muestran en las coordenadas de la audioconferencia, se pueden configurar para usar:

-   Valor predeterminado para el espacio empresarial.

-   Los números de teléfono de puente de conferencia asignados automáticamente.

-   Un puente de conferencia números de teléfono que se han configurado manualmente para cada usuario.

Los números de teléfono de puente de conferencia específicos del usuario suelen ser útiles en organizaciones globales o de Nationwide donde los usuarios se distribuyen y deben proporcionar números locales como números de teléfono predeterminados para las invitaciones a reuniones.

Los participantes que se unen desde distintas ciudades o en el extranjero pueden buscar números adicionales configurados en el nivel del espacio empresarial, pero estos números no aparecen directamente en las invitaciones a reuniones. Las invitaciones a reuniones proporcionan un vínculo que lleva a los participantes a la página de **números de acceso telefónico de conferencia** de los equipos para que busquen el número de teléfono del puente de conferencia más cercano a su ubicación.

También puede configurar la forma en que el organizador de la reunión controla las llamadas no autenticadas (si desea que el organizador de la reunión pueda iniciar la reunión antes de que las personas que llamen no se autentiquen o permitir que los autores de llamadas no autenticados inicien una reunión) .

También puede aplicar configuraciones adicionales para que cada usuario controle el uso de números de teléfono de puente de conferencia gratuitos y el acceso telefónico desde una conferencia.

> [!NOTE]
> Estos controles relacionados con los costes solo están disponibles en este momento para clientes de la versión preliminar. Puede inscribir su organización en el programa de previsualización desde https://www.skypepreview.com.

Con estos controles, puede decidir si los organizadores de reuniones pueden proporcionar números de teléfono de puente de conferencia gratuitos para las reuniones organizadas por ellos, y si los participantes pueden marcar desde las reuniones que han organizado. El nivel de intervalo de control de llamadas salientes evita que se eviten las llamadas, para permitir el acceso telefónico a números nacionales e internacionales únicamente

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si su organización requiere notificaciones de entrada y salida y, si lo hace, el tipo de notificación que se va a implementar (tonos, número de teléfono o nombre grabado).</li><li>Decida la longitud del PIN de audioconferencia que cumple los requisitos de seguridad de su organización.</li><li>Decida si su organización desea tomar el control de las comunicaciones de los usuarios relacionados con el servicio de audioconferencia.</li><li>Decidir los números de teléfono del puente de conferencia que se asignarán a cada organizador de la reunión.</li><li>Decida si algunos organizadores de reuniones necesitan usar números de teléfono de puente de conferencia gratuitos para sus reuniones.</li><li>Decidir si algunos organizadores de reuniones necesitan permitir que los autores de llamadas no autenticadas inicien una reunión.</li><li>Decida si algunos organizadores de reuniones necesitan un acceso telefónico de conferencia para su control.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente la configuración de puentes de conferencia con todos los detalles (notificaciones de entrada y salida, longitud de PIN y notificación por correo electrónico de cambios en la configuración).</li><li>Documente los números de teléfono de los puentes de conferencia que se asignarán a cada organizador de la reunión y la configuración correspondiente para controlar la Directiva para los llamadores no autenticados y los controles de acceso telefónico y gratuito.</li></ul>|

> [!TIP]
> La configuración del puente de conferencia se puede documentar como en el ejemplo siguiente.
> 
> |         |         |
> |---------|---------|
> |Habilitar las notificaciones de entrada y salidas de las reuniones|Habilitado|
> |Tipo de anuncio de entrada/salida|Tonos|
> |Pedir a los autores de llamada que graben su nombre antes de unirse a la reunión|Deshabilitado|
> |Longitud de PIN|5|
> |Enviar correos automáticamente a los usuarios si cambia su configuración de acceso telefónico|Deshabilitado|

<br>

> [!TIP]
> Puede documentar la lista de asignación de configuración de puentes de conferencia para los usuarios de la Conferencia de audio mediante el ejemplo siguiente.
>
> |Usuario  |Oficina  |Número de pago predeterminado  |Número gratuito predeterminado  |Permitir número gratuito  |Los autores de llamadas sin autenticar no pasan por la sala de espera  |Llamadas desde la conferencia  |
> |---------|---------|---------|---------|---------|---------|---------|
> |Adele Vance|One Epping Road|Por añadir|Por añadir|Sí|Habilitado|Internacionales y nacionales|
> |Alex Wilber|One Epping Road|Por añadir|Por añadir|No|Deshabilitado|No se permiten|
> |Ben Walters|One Epping Road|Por añadir|Por añadir|No|Deshabilitado|No se permiten|
> |Christie Cline|One Marina Boulevard|Por añadir|Por añadir|Sí|Deshabilitado|Nacionales|
> |Debra Berger|One Marina Boulevard|Por añadir|Por añadir|Sí|Habilitado|Nacionales|
> |Lee Gu|One Marina Boulevard|Por añadir|Por añadir|Sí|Habilitado|Nacionales|
> |Emily Braun|32 London Bridge Street|+44 20 7946 0001|Por añadir|Sí|Habilitado|No se permiten|
> |Lidia Holloway|32 London Bridge Street|+44 20 7946 0001|Por añadir|Sí|Deshabilitado|No se permiten|
> |Louis Lahr|32 London Bridge Street|+44 20 7946 0001|Por añadir|Sí|Deshabilitado|No se permiten|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Por añadir|Por añadir|No|Deshabilitado|Nacionales|
> |Rachelle Cormier|39 quai du Président Roosevelt|Por añadir|Por añadir|Sí|Habilitado|Internacionales y nacionales|
> |Isabell Potvin|39 quai du Président Roosevelt|Por añadir|Por añadir|No|Deshabilitado|Nacionales|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Administrar números de teléfono de voz de nube

Para la implementación de audioconferencias, puedes elegir adquirir nuevos números de teléfono o transferir o transferir números de teléfono existentes.

Para permitir que los usuarios marquen números de teléfono de la forma en que están acostumbrados, como por ejemplo, omitir códigos de área para llamadas locales, omitir el código de país para llamadas nacionales o incluso usar el marcado de dígitos cortos al realizar la llamada en conferencia, puede configurar un plan de marcado personalizado y asignarla a los usuarios.

## <a name="acquire-new-telephone-numbers"></a>Adquirir nuevos números de teléfono

Los dos tipos de números de teléfono de las soluciones de voz en la nube de Microsoft son:

-   Números de suscriptor (usuario), que se pueden asignar a los usuarios de su organización.

-   Números de servicio, disponibles como números de servicio de pago y gratuitos, que tienen una capacidad de llamadas simultáneas superior a los números de suscriptor y se pueden asignar a servicios como audioconferencias, operadores automáticos o colas de llamadas.

Para obtener más información sobre estos tipos de números de teléfono, vea [diferentes tipos de números de teléfono para los planes de llamadas](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

El recuento total de números de teléfono que puede obtener depende de los tipos de números de teléfono y de la cantidad de licencias que haya comprado y asignado a los usuarios.

Cuando se trata de números de servicio, debe planificar cuidadosamente su implementación de audioconferencias. Evaluar si su empresa necesita números de teléfono de un puente de conferencia dedicado; en caso contrario, su organización puede optar por usar números de teléfono de puente de conferencia compartidos.

Para obtener más información sobre el recuento total de números de teléfono que puede obtener, consulte ¿cuántos [números de teléfono puede obtener?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir las ubicaciones de los usuarios o las oficinas en las que recibirán nuevos números de teléfono de Microsoft.</li><li>Decidir el tipo de números de teléfono que se van a adquirir de Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente las ubicaciones o ubicaciones de los usuarios en las que recibirán nuevos números de teléfono de Microsoft.</li><li>Documente el tipo de números de teléfono que se van a adquirir de Microsoft.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transferir números de teléfono existentes

Si su organización desea transferir (o trasladar) números de teléfono existentes a Microsoft, puede hacerlo enviando una solicitud de portabilidad a Microsoft.

Puede transferir todos los números de teléfono existentes a la vez (puerto completo) y, en algunos mercados, puede transferir un subconjunto de los números de teléfono existentes (puerto parcial). Un puerto parcial puede ser útil en aquellos casos en los que solo quiera mover el puente de conferencia de acceso telefónico local al servicio de audioconferencia.

Una única solicitud de portabilidad puede transferir los números de teléfono a un único tipo de número de teléfono. Si necesita transferir algunos números de teléfono como números de suscriptor y otros como números de servicio, le recomendamos que complete primero la transferencia a Microsoft y, después, realice la conversión en cuanto los números estén dentro del control de Microsoft.

Como alternativa, si se admite el puerto parcial, puede enviar varias solicitudes de portabilidad, una solicitud de puerto por vez. Sin embargo, este enfoque alternativo prolongará tu contrato con tu proveedor de servicios de telecomunicaciones existente.

El traslado de números de teléfono es un tema complejo y requiere una planificación, coordinación y una administración adecuada de las expectativas de los participantes. Para obtener más información, vea los artículos siguientes:

-   [Transferir números de teléfono a Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Preguntas comunes sobre la transferencia de números de teléfono](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decidir las ubicaciones de los usuarios o las oficinas donde se transferirán los números de teléfono existentes a Microsoft.</li><li>Decidir el tipo de números de teléfono que se transferirán a Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente las ubicaciones o ubicaciones de los usuarios donde se transferirán los números de teléfono existentes a Microsoft.</li><li>Documente el tipo de números de teléfono que se transferirán a Microsoft.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Planes de marcado

Un plan de marcado de la característica de sistema telefónico de Office 365 es un conjunto de reglas de normalización que traduce los números de teléfono marcados a un formato alternativo (por lo general, formato E. 164) para la autorización de llamadas y enrutamiento de llamadas. El servicio de audioconferencia aprovecha las mismas capacidades usadas por el sistema telefónico para traducir números de teléfono marcados en escenarios de aceptación de llamada en conferencia (por ejemplo, invitar a participantes a través de RTC y llamar a la característica "Llamarme").

En la característica del sistema telefónico de Office 365, hay dos tipos de planes de marcado:

-   **Plan de marcado de servicios:** Este es el plan de marcado predeterminado que se aplica a los usuarios en función de su ubicación de uso de Office 365 y no se puede modificar.

-   **Plan de marcado de inquilino:** Este es un plan de marcado personalizable dentro de un espacio empresarial, que se divide en dos tipos:

    -   **Inquilino-plan de marcado global:** El plan de marcado que se aplica a todos los usuarios del inquilino.

    -   **Inquilino-plan de marcado de usuario:** El plan de marcado que solo se aplica a usuarios específicos.

El plan de marcado eficaz asignado a los usuarios es la combinación del plan de marcado de servicios (basado en la ubicación de uso de Office 365 de un usuario) y el plan de marcado de inquilino (puede ser un inquilino con plan de marcado global o un plan de marcado de usuario de inquilino).

En la ![tabla se muestran tres combinaciones de planes de servicio y de acceso telefónico de inquilino.] En la (media/audio_conferencing_image8.png "tabla se muestran tres combinaciones de planes de servicio y de acceso telefónico de inquilino.")

> [!Important]
> Puede haber un máximo de 25 reglas de normalización en cada plan de marcado de inquilino; por lo tanto, es importante evitar duplicar las reglas de normalización que ya están disponibles como parte del plan de marcado del servicio.

Para obtener más información sobre los planes de marcado, vea [¿Qué son los planes de marcado?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Puntos de decisión|<ul><li>Decida si su organización requiere planes de marcado personalizados (requisitos empresariales, requisitos de adopción, etc.).</li><li>Si corresponde, decida el ámbito del plan de marcado de inquilino (inquilino global o de inquilino-usuario) para cumplir los requisitos de los planes de marcado personalizados.</li><li>Si corresponde, decida los planes de marcado de inquilino que creará para admitir ubicaciones de usuario o oficinas en el ámbito de la implementación de voz en la nube.</li><li>Si corresponde, decida qué usuarios requieren un plan de marcado personalizado y el plan de marcado de inquilino que se asignará a cada usuario.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Pasos siguientes|<ul><li>Documente los planes de marcado personalizados y las reglas de normalización asociadas que deben configurarse como parte de la implementación de voz en la nube.</li><li>Documente los usuarios a los que se les va a asignar un plan de marcado personalizado y el plan de marcado de inquilino que se asignará a cada usuario.</li></ul>|

> [!TIP]
> Si es aplicable a su proyecto, puede usar la siguiente plantilla para documentar las configuraciones de los planes de marcado de inquilino.
> 
> |Nombre de plan de marcado de inquilino<br>_Descripción_  |Nombre de reglas de normalización<br>_Descripción_  |Patrón<br>Traducción<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_Plan de marcado de One Epping Road North Ryde, NSW, AU_|**AU-NSW-NorthRyde-OER-Internal**<br>_Número interno (x7000 - x7999) para oficina de One Epping Road, North Ryde, NSW, Australia_|^ (7 \ d{3}) $<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_Normalización de número local para NSW, Australia_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
> ||**AU-TollFree**<br>_Normalización de número gratuito para Australia_|^ (1 [38] \d{4,8}) \d * $<br>+61$1<br>False|
> ||**AU-Service**<br>_Normalización de número de servicio para Australia_|^ (000\|1 [0125] \d{1,8}) $<br>1 $<br>False|
> |**SG-Singapore-OMB**<br>_Plan de marcado de OMB Singapore, SG_|**SG-OMB-Internal**<br>_Número interno (x8000 â € "x8999) para OMB Office, Singapur_|^ (8 \ d{3}) $<br>+656888$1<br>True|
> ||**SG-TollFree**<br>_Normalización de número gratuito para Singapur_|^ (1? 800 \ d{7}) \d * $<br>+65$1<br>False|
> ||**SG-Service**<br>_Normalización de número de servicio para Singapur_|^ (1 \ d{3,4}\|9 \ d{2}) $<br>1 $<br>False|
> |**FR-Paris-Issy-39qdPR**<br>_Plan de marcado de 39 quai du Président Roosevelt Issy-les-Moulineaux, Francia_|**FR-39qdPR-Internal**<br>_Número interno (x7000 â € "x7999) para 39 Quai du Président Roosevelt Office, Issy-les-Moulineaux, Francia_|^ (7 \ d{3}) $<br>+3319999$1<br>True|
> ||**FR-TollFree**<br>_Normalización de número gratuito para Francia_|^ 0? (80 \ d{7}) \d * $<br>+33$1<br>False|
> ||**FR-Service**<br>_Normalización de número de servicio para Francia_|^ (1 \ d{1,2}\|11 [68] \d{3}\|10 \ d{2}\|3 \ d{3}) $<br>1 $<br>False|

<br>

> [!TIP]
> La plantilla de ejemplo siguiente se puede utilizar para documentar las asignaciones de planes de marcado de su proyecto:
>
> |Usuario  |Oficina  |Tipo de plan de marcado  |Nombre de plan de marcado  |
> |---------|---------|---------|---------|
> |Adele Vance|One Epping Road|Plan de marcado de inquilino|AU-NSW-NorthRyde-OER|
> |Alex Wilber|One Epping Road|Plan de marcado de inquilino|AU-NSW-NorthRyde-OER|
> |Ben Walters|One Epping Road|Plan de marcado de inquilino|AU-NSW-NorthRyde-OER|
> |Christie Cline|One Marina Boulevard|Plan de marcado de inquilino|SG-Singapore-OMB|
> |Debra Berger|One Marina Boulevard|Plan de marcado de inquilino|SG-Singapore-OMB|
> |Lee Gu|One Marina Boulevard|Plan de marcado de inquilino|SG-Singapore-OMB|
> |Emily Braun|32 London Bridge Street|Plan de marcado de servicio|N/D|
> |Lidia Holloway|32 London Bridge Street|Plan de marcado de servicio|N/D|
> |Louis Lahr|32 London Bridge Street|Plan de marcado de servicio|N/D|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|Plan de marcado de inquilino|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Decisiones del servicio de documentos 

Use la información de las secciones anteriores de este artículo para documentar las decisiones de servicio. En general, en esta documentación se incluyen las siguientes secciones principales:

-   Lista de habilitación del sitio de servicio de Audioconferencia

-   Lista de asignación de licencias para los organizadores de reuniones de Audioconferencia

-   Números de planificación de Créditos de comunicaciones

-   Detalles de puentes de conferencia

-   Configuración de puentes de conferencia

-   Asignaciones de configuraciones de puentes de conferencia

-   Planes de adquisición de números de teléfono

-   Planes de marcado de inquilino

-   Asignaciones de planes de marcado

<!--ENDOFSECTION-->