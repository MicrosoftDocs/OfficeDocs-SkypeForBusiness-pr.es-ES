---
title: Control de administración de inquilinos para el reconocimiento de voz (perfil de voz) en Salas de Teams
author: dstrome
ms.author: dstrome
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre el control de administración de inquilinos para el reconocimiento de voz (perfil de voz) en las salas de reuniones de Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
appliesto:
- Microsoft Teams
ms.openlocfilehash: 478e739be2787eb2758a2070a441f68c7da727ba
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438308"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a>Administrar los controles de tecnología de reconocimiento de voz para un altavoz inteligente

Un orador inteligente usa información de perfil de voz para reconocer quién dijo qué en la transcripción en vivo. Cuando una Salas de Microsoft Teams de la sala de reuniones de Windows está equipada con un altavoz inteligente, se puede usar la transcripción en directo durante la reunión. En este artículo se explica cómo usted, un administrador de inquilinos, controlar la generación de perfiles de voz que se usa para el reconocimiento de voz para generar la transcripción en directo. Puede controlar hasta qué grado usa la organización el reconocimiento de voz y las siguientes características:

- Edite el nombre del orador en las transcripciones.
- Cambie el orador de una sola expresión en la transcripción o cambie el orador en todas las expresiones de la transcripción (pero no en las transcripciones futuras).
- Cambie la identificación del orador de las personas que aparecen en la reunión.
- Quite la identificación de una o más expresiones identificadas como ese orador en cada transcripción.

## <a name="review-intelligent-speaker-requirements"></a>Revisar los requisitos del altavoz inteligente

Un altavoz inteligente incluye una matriz especial de siete micrófonos. El sistema usa información de perfil de voz para identificar las voces de hasta 10 personas en las salas de reuniones.

Los siguientes elementos son requisitos del altavoz inteligente:

- La sala de reuniones debe tener un máximo de 10 personas presentes en persona.
- La sala de reuniones tiene un vínculo de carga de 7 Mbps como mínimo.

Son compatibles los altavoces inteligentes Epos, Sennheiser y Yealink.

> [!NOTE]
> El altavoz inteligente está disponible en todos los países y regiones. Consulte [Configuraciones regionales admitidas](#supported-locales) para obtener una lista de las configuraciones regionales compatibles actualmente con la inscripción biométrica y la transcripción en la reunión.

## <a name="set-up-an-intelligent-speaker"></a>Configurar un altavoz inteligente

Un altavoz inteligente se conecta directamente mediante USB a la consola de Salas de Teams.

> [!NOTE]
> **Debe** usarse un altavoz inteligente Yealink con una consola Yealink.

> [!NOTE]
> No se admite un altavoz inteligente conectado a Logitech Surface Pro Salas de Microsoft Teams. Hay un problema conocido que Salas de Teams no puede reconocer el altavoz inteligente a través de la base.

Un altavoz inteligente debe colocarse al menos a 20 cm (8 pulgadas) de las paredes y objetos grandes, como portátiles. Si el cable USB del altavoz inteligente no es lo suficientemente largo para la configuración, usa extensores de cable.

1. Inicia sesión en la consola como administrador.
2. Establezca la configuración del dispositivo de Teams para que coincida con el altavoz y el micrófono del altavoz inteligentes.
   Usted también puede hacer esto a través del portal TAC en lugar de en la consola de la sala.

   El diagrama muestra cómo se conecta el altavoz inteligente al dispositivo si el dispositivo incluye un cuadro de datos.

   ![Configuración del altavoz inteligente con el altavoz, la caja de energía y datos. Una línea va al puerto USB de la consola y la otra a la corriente.](../media/intelligent-speakers1.png)

   El diagrama muestra cómo se conecta el altavoz inteligente al dispositivo si el dispositivo no incluye un cuadro de datos.

   ![Configuración del altavoz inteligente con el altavoz que se conecta directamente a la consola.](../media/intelligent-speakers2.png)

> [!NOTE]
> Los dispositivos EPOS y Yealink deben tener prefijo "EPOS" o "Yealink" y contener "UAC2_RENDER" en el nombre del altavoz y "UAC2_TEAMS" en el nombre del micrófono. Si no encuentras estos nombres de micrófono y altavoz en el menú desplegable, reinicia el dispositivo Altavoz inteligente.

## <a name="enable-an-intelligent-speaker-user-recognition"></a>Habilitar un reconocimiento de usuario de altavoz inteligente

Los datos de perfil de voz se pueden usar en cualquier reunión con un altavoz inteligente. Vea [Directivas de reuniones de Teams](../meetings-policies-recording-and-transcription.md#transcription) y [los cmdlets de reuniones de PowerShell](/powershell/module/skype/set-csteamsmeetingpolicy) para obtener información sobre la configuración de la reunión.

Los datos del perfil de voz del usuario se crean cuando la directiva se establece para distinguir o cuando un invitado que no es de la reunión entra durante la reunión. Los datos del perfil de voz se descartan al final de la reunión.

Las siguientes son las directivas necesarias para establecer un altavoz inteligente y el reconocimiento de usuario.

|Directiva|Descripción|Valores y comportamiento|
|-|-|-|
|enrollUserOverride|Se usa para establecer la captura de perfil de voz o la inscripción en la configuración de Teams para un inquilino. |**Deshabilitado**<br><ul><li> Los usuarios que nunca se han inscrito no pueden ver, inscribirse ni volver a inscribirse.<li>El punto de entrada al flujo de inscripción se ocultará.<li>Si los usuarios seleccionan un vínculo a la página de inscripción, verán un mensaje que indica que esta característica no está habilitada para su organización.  <li>Los usuarios inscritos pueden ver y quitar su perfil de voz en la configuración de Teams. Una vez que quiten su perfil de voz, no podrán ver, acceder ni completar el flujo de inscripción.</li></ul><br>**Habilitado**<br><ul><li> Los usuarios pueden ver, acceder y completar el flujo de inscripción.<li>El punto de entrada se mostrará en la página de configuración de Teams, en la pestaña **Reconocimiento** .</li></ul>|
|roomAttributeUserOverride|Controle la identificación de usuario basada en voz en las salas de reuniones. Esta configuración es necesaria para las cuentas de Salas de Teams.| **Desactivado**<br><ul><li>El dispositivo Salas de Teams no enviará ancho de banda para guardar la secuencia de audio desde la sala. <li>Los usuarios de las salas de reuniones no se atribuirán ni distinguirán, y sus firmas de voz no se recuperarán ni se usarán en absoluto.<li>Se desconocen los usuarios de las salas de reuniones.</li></ul> <br>**Atributo**<br><ul><li>Los usuarios de salas se atribuirán en función de su estado de inscripción.<li>Los usuarios inscritos se muestran con su nombre en la transcripción.  <li>Los usuarios que no están inscritos se muestran como oradores \<n>.<li>El dispositivo Salas de Teams enviará siete transmisiones de audio desde la sala.</ul> <br>**Distinguir**<br> <ul><li>Los usuarios de las salas se distinguirán y separarán como altavoz 1, altavoz 2, .... orador \<n> en la transcripción.</li><li>Independientemente del estado de inscripción del usuario, su nombre no se mostrará en la transcripción.</li><li>El dispositivo Salas de Teams enviará siete transmisiones de audio desde la sala.</li></ul>
|AllowTranscription|Necesario para las cuentas de usuarios y salas de Teams.|**Verdadero** y **falso**|
||||

En el Centro de administración de Teams, establezca la directiva **de transcripción** . La configuración está **desactivada** de forma predeterminada.

![el centro de administración con las directivas de reunión resaltadas y permitir la transcripción seleccionado.](../media/allow-transcription1.png)
  
> [!NOTE]
> Después de asignar una directiva, pueden tardar hasta 48 horas en surtir efecto. Para que la directiva surta efecto antes, es necesario cerrar la sesión de las cuentas y volver a iniciarla.

## <a name="frequently-asked-questions-faq"></a>Preguntas más frecuentes (P+F)

**¿Dónde se almacenan los datos del perfil de voz?**

Los datos de perfil de voz se almacenan en Office 365 nube con contenido de usuario.

**¿Cuál es la escala de tiempo y la directiva de retención?**

La directiva de retención general se indica en Información [general sobre retención de datos](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview). Además, los datos del perfil de voz de un usuario se eliminarán después de 1 año si el usuario no está invitado a ninguna reunión con un orador inteligente dentro de ese período de un año. Los datos no se usan en ninguna reunión para empleados existentes. Si un empleado ha abandonado la compañía, los datos del perfil de voz se consideran contenido de usuario y se tratan como tales por Office 365 directiva de retención de datos que se describe en información [general de retención de datos](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

**¿Se usan los datos de perfil de voz en los servicios de Microsoft?**

No, los datos del perfil de voz solo se usan para los fines para los que el usuario ha dado su consentimiento. Microsoft no usará los datos del perfil de voz excepto en los escenarios de reconocimiento de voz de Teams.

Por ejemplo, Microsoft no usará los datos en las situaciones siguientes:

**¿Se usan mis datos de perfil de voz al unirse a una reunión en otra organización?**

No solo en reuniones organizadas por un usuario de su organización.

**¿Cómo puedo exportar mi perfil de voz?**

El administrador de TI puede exportar los datos de audio en cualquier momento.

## <a name="supported-locales"></a>Configuraciones regionales compatibles

Las siguientes configuraciones regionales de transcripción y de inscripción en la reunión son compatibles en todos los países y regiones.

### <a name="enrollment-locales"></a>Configuraciones regionales de inscripción

Los usuarios finales pueden inscribir sus voces para el reconocimiento en las configuraciones regionales siguientes:

|**Idioma**|**País o región**|**Id. de referencia cultural**|
|:-----|:-----|:-----|
|Árabe  <br/> |Arabia Saudí <br/> |ar-SA  <br/> |
|Chino  <br/> |China <br/> |zh-CN  <br/> |
|Chino  <br/> |Taiwán <br/> |zh-TW  <br/> |
|Danés  <br/> |Dinamarca <br/> |da-DK  <br/> |
|Neerlandés  <br/> |Países Bajos <br/> |nl-NL  <br/> |
|Inglés  <br/> |Australia <br/> |en-AU  <br/> |
|Inglés  <br/> |Canadá  <br/> |en-CA <br/> |
|Inglés  <br/> |India  <br/> |en-IN  <br/> |
|Inglés  <br/> |Nueva Zelanda  <br/> |en-NZ  <br/> |
|Inglés  <br/> |Reino Unido  <br/> |en-GB  <br/> |
|Inglés  <br/> |Estados Unidos  <br/> |en-US  <br/> |
|Finés  <br/> |Finlandia  <br/> |fi-FI  <br/> |
|Francés  <br/> |Canadá <br/> |fr-CA  <br/> |
|Francés  <br/> |Francia <br/> |fr-FR  <br/> |
|Italiano  <br/> |Italia <br/> |it-IT  <br/> |
|Japonés  <br/> |Japón <br/> |ja-JP  <br/> |
|Noruego  <br/> |Noruega <br/> |nb-NO  <br/> |
|Polaco  <br/> |Polonia <br/> |pl-PL  <br/> |
|Portugués      <br/> |Brasil <br/> |pt-BR  <br/> |
|Ruso  <br/> |Rusia <br/> |ru-RU  <br/> |
|Sueco  <br/> |Suecia <br/> |sv-SE  <br/> |
|Español  <br/> |México  <br/> |es-MX  <br/> |
|Español  <br/> |España  <br/> |es-ES  <br/> |

### <a name="in-meeting-transcription-locales"></a>Configuraciones regionales de transcripción durante la reunión

Una vez que un usuario final se inscribe, su voz se puede reconocer durante las reuniones e identificarse en la transcripción cuando la reunión se establece en una de las siguientes configuraciones regionales:

|**Idioma**|**País o región**|**Id. de referencia cultural**|
|:-----|:-----|:-----|
|Chino (simplificado)  <br/> |China  <br/> |zh-CN  <br/> |
|Inglés  <br/> |Australia <br/> |en-AU  <br/> |
|Inglés  <br/> |Canadá  <br/> |en-CA <br/> |
|Inglés  <br/> |India  <br/> |en-IN  <br/> |
|Inglés  <br/> |Nueva Zelanda  <br/> |en-NZ  <br/> |
|Inglés  <br/> |Reino Unido  <br/> |en-GB  <br/> |
|Inglés  <br/> |Estados Unidos  <br/> |en-US  <br/> |
|Francés  <br/> |Canadá  <br/> |fr-CA  <br/> |
|Francés  <br/> |Francia  <br/> |fr-FR  <br/> |
|Alemán  <br/> |Alemania  <br/> |de-DE  <br/> |
|Italiano  <br/> |Italia  <br/> | it-IT <br/> |
|Japonés  <br/> |Japón  <br/> |ja-JP  <br/> |
|Coreano  <br/> |Corea  <br/> |ko-KR  <br/> |
|Portugués  <br/> |Brasil  <br/> |pt-BR  <br/> |
|Español  <br/> |México  <br/> |es-MX  <br/> |
|Español  <br/> |España  <br/> |es-ES  <br/> |

## <a name="related-topics"></a>Temas relacionados

[Artículo de soporte técnico: Usar altavoces inteligentes para identificar a los participantes en la sala](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
