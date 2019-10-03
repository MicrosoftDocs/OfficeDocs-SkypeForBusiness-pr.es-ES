---
title: ¿Qué son los operadores automáticos en la nube?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.date: 4/2/2019
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.autoattendants.overview
ms.custom:
- Phone System
description: Aprenda Cuáles son los operadores automáticos de la nube y cómo usarlos.
ms.openlocfilehash: fd1fd053c0ecab8e0a36835f6d26127db91431be
ms.sourcegitcommit: 2d31209aae9e0171693389db97b0b5c974864673
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37375692"
---
# <a name="what-are-cloud-auto-attendants"></a>¿Qué son los operadores automáticos en la nube?

El sistema telefónico en Office 365 proporciona operadores automáticos, que se pueden usar para permitir que los autores de llamadas externos e internos se muevan a través de un sistema de menús para ubicar y realizar llamadas a usuarios o departamentos de la empresa en su organización.
  
Un operador automático es una serie de mensajes de voz o archivos de audio que escuchan las personas que llaman en lugar de un operador humano cuando llaman a una organización. Cuando las personas llaman a un número asociado con un operador automático, sus elecciones pueden redirigir la llamada a un usuario o localizar a alguien de su organización y, a continuación, conectarse a ese usuario. Pueden expresar sus elecciones e interactuar con el sistema de menús mediante el teclado de un teléfono (DTMF) o el reconocimiento de voz.
  
Para configurar un operador automático para el sistema telefónico en Office 365, vaya a [configurar un operador automático](create-a-phone-system-auto-attendant.md)de la nube.
  
Un operador automático de la nube tiene las siguientes características:
  
- Puede transmitir saludos corporativos o informativos.
- Puede proporcionar menús corporativos personalizados. Estos menús se pueden personalizar para que tengan más de un nivel.
- Proporciona búsqueda en directorios que permite a las personas que llaman para buscar un nombre en el directorio de la organización.
- Permite que alguien que llama para llegar a un mensaje o abandonarlo para una persona de su organización.
- Admite varios idiomas para avisos, texto a voz y reconocimiento de voz.
- Es compatible con la especificación de festivos y horario laboral.
- Admite la transferencia de llamadas a un operador, otros usuarios, colas de llamadas y operadores automáticos.

> [!NOTE]
> Este artículo se aplica a Microsoft Teams y a Skype empresarial online.

## <a name="getting-started"></a>Introducción

Para comenzar a utilizar operadores automáticos, es importante recordar que:

- Es necesario un operador automático para tener una cuenta de recursos asociada. Para obtener más información sobre las cuentas de recursos, consulte [administrar cuentas de recursos en Teams](manage-resource-accounts.md) .
- Si va a asignar un número de teléfono a una cuenta de recursos, ahora puede usar la licencia de usuario virtual del sistema telefónico de sistema de costos. Esto proporciona capacidades de sistema telefónico a números de teléfono en el nivel de la organización y le permite crear funciones de cola de llamadas y de operador automático.

> [!NOTE]
> Los números del servicio de enrutamiento directo del operador automático y las colas de llamadas solo se admiten para los usuarios y agentes de Microsoft Teams.
  
   > [!TIP]
   > Para redirigir llamadas a un operador o una opción de menú que sea un usuario en línea con una licencia de **sistema telefónico** , tendrá que habilitarlos para telefonía IP empresarial o asignarles planes de llamada. Consulte [asignar licencias de Microsoft Teams](assign-teams-licenses.md). También puede usar Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obtener y usar números de servicio gratuitos para sus operadores automáticos, debe configurar créditos de comunicaciones. Para ello, vea [¿Qué son los créditos de las comunicaciones?](what-are-communications-credits.md) y [configurar créditos de comunicaciones para su organización](set-up-communications-credits-for-your-organization.md).

    > [!IMPORTANT]
    > Los números de teléfono de usuario (suscriptor) no se pueden asignar a los operadores automáticos; solo se pueden usar números de teléfono de servicio de pago y gratuitos.

- Normalmente, un sistema de operador automático completo implica varios operadores automáticos y es posible que solo requiera un único número de teléfono asignado para el operador automático de nivel superior o entrada. Otros operadores automáticos o colas de llamadas en el sistema completo solo necesitarán un número de teléfono si desea proporcionar varios puntos de entrada en el sistema.
- Es posible aplicar más de un número de teléfono a un operador automático asociando más de una cuenta de recursos a un operador automático.
  
## <a name="feature-overview"></a>Descripción general de la característica

### <a name="dial-by-name"></a>Marcado por nombre

El marcado por nombre es una característica de un operador automático que también se conoce como búsqueda de directorio. Permite que las personas que llaman a su operador automático usen la voz (reconocimiento de voz) o las respuestas del teclado (DTMF) para escribir un nombre completo o parcial para buscar en el directorio de la empresa, ubicar a la persona y, a continuación, transferir la llamada. No es necesario que los usuarios que desean encontrarse con el método de marcado por nombre **tengan un número de teléfono o tengan asignados planes de llamadas, pero deben tener una licencia de sistema telefónico si son usuarios conectados, o bien EV habilitado para usuarios locales**. Es posible que el marcado por nombre pueda buscar y transferir llamadas a los usuarios de Microsoft teams que se hospedan en diferentes países o regiones para organizaciones multinacionales.

### <a name="maximum-directory-size"></a>Tamaño máximo de directorio

No hay ningún límite en el tamaño de Active Directory para el que se admite el marcado por nombre al usar el teclado del teléfono para buscar la escritura de nombres parciales o completos (nombre + apellidos y también Apellidos + nombre). Sin embargo, el tamaño de la lista de nombres máximo que un solo operador automático puede admitir mediante el reconocimiento de nombres con voz es de 80.000 usuarios.
  
|Tipo de entrada|Formato de búsqueda|Número máximo de usuarios en una organización|
|:-----|:-----|:-----|
|DTMF (entrada con teclado) |Parcial  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre |Sin límite  |
|Voz (entrada de voz) |FirstName  <br/> Apellidos  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre  | 80.000 usuarios |

> [!NOTE]
> Si usa el marcado por nombre con reconocimiento de voz, pero el directorio activo de su organización es superior a 80.000 usuarios y no ha limitado el ámbito de marcado por nombre con la característica de ámbito de marcado, el marcado por nombre seguirá funcionando con las personas que llamen con el teclado del teléfono y las entradas de voz estarán disponibles para todos los demás escenarios. Puede usar la característica de ámbito de marcado para limitar los nombres que se pueden contactar cambiado el ámbito de Marcado por nombre de un operador automático determinado.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Marcado por nombre: entrada mediante teclado (DTMF)
Las personas que llaman pueden usar el marcado por nombre para comunicarte con los usuarios especificando el nombre completo o parcial de la persona a la que están tratando de llegar. Hay varios formatos que pueden usarse cuando se escribe el nombre.

Para realizar búsquedas en el directorio de su organización, los usuarios pueden usar la tecla 0 (cero) para indicar un espacio entre el nombre y el apellidos, o viceversa. Cuando escriban el nombre, se les pedirá que terminen la entrada del teclado con la tecla #. Por ejemplo, "Después de introducir el nombre de la persona que busca, pulse #". Si se encuentran varios nombres, se proporcionará una lista de nombres al autor de la llamada para que seleccione uno.
  
Las personas pueden realizar búsquedas por nombre en su organización empleando los siguientes formatos de búsqueda con el teclado del teléfono:
  
|Formato de nombre|Tipo de búsqueda|Ejemplo|Resultado de búsqueda|
|:-----|:-----|:-----|:-----|
|Nombre + Apellidos |Completo  |Amos0Marble# |Amos Marble |
|Apellidos + Nombre |Completo |Marble0Amos#  |Amos Marble |
|FirstName  |Completo   |Amos#   |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus |
|Apellidos |Completo |Marble#  |Pulse 1 para Amos Marble  <br/> Pulse 2 para Mary Marble |
|Nombre o Apellidos |Parcial |Mar# |Pulse 1 para Mary Marble  <br/> Pulse 2 para Mary Jones  <br/> Pulse 3 para Amos Marcus |
|Nombre + Apellidos |Parcial |Mar0Amos# |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus |
|Apellidos + Nombre |Parcial |Mar0Am# |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus |

En las búsquedas de personas a través del teclado del teléfono se pueden utilizar diferentes caracteres especiales. Por ejemplo, se le solicitará a la persona que use la tecla almohadilla (#), mientras que la tecla cero (0) se usa para un espacio entre nombres. Al pulsar la tecla de asterisco (*) se repetirá la lista de nombres coincidentes.
  
|Carácter especial del teclado del teléfono|Significado|
|:-----|:-----|
|#   |Carácter de fin al introducir un nombre. |
|,0   |Espacio entre nombres. |
|*    |Repetir la lista de nombres coincidentes. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Marcado por nombre: reconocimiento de nombres por voz

Los usuarios pueden buscar a otros usuarios de su organización mediante la voz (reconocimiento de voz). También pueden comunicarse con cualquier persona de Active Directory de la empresa diciendo el nombre de la persona que está tratando de ubicar. El uso de entradas de voz puede reconocer nombres en varios formatos, como FirstName, LastName, FirstName + LastName o LastName + Name.
  
Al habilitar el reconocimiento de voz para un operador automático, la entrada del teclado de teléfono (DTMF) no se deshabilitará, por lo que se pueden usar ambos tipos de entrada. La entrada del teclado del teléfono no se puede deshabilitar y se puede usar en cualquier momento, incluso si el reconocimiento de voz está habilitado en el operador automático.
  
Al igual que sucede con la entrada mediante el teclado del teléfono, si se encuentran varios nombres, se proporcionará una lista de nombres al autor de la llamada para que seleccione uno.
  
Los autores de llamadas pueden decir los nombres en los siguientes formatos:
  
|Nombre con voz|Tipo de búsqueda|Ejemplo|Resultado de búsqueda|
|:-----|:-----|:-----|:-----|
|Nombre + Apellidos |Completo |Amos Marble |Amos Marble |
|Apellidos + Nombre |Completo  |Marble Amos |Amos Marble |
|FirstName |Completo |Amos |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Amos Jones |
|Apellidos |Completo |Marble |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Ben Marble |

> [!NOTE]
> Es posible que tarde hasta 36 horas para que un nuevo usuario tenga su nombre en el directorio de marcado por nombre con reconocimiento de voz debido al retraso de replicación de Active Directory.
  
### <a name="language-support"></a>Compatibilidad con idiomas

La característica de texto a voz está disponible en los siguientes idiomas:
  
||||
|:-----|:-----|:-----|
|Árabe (EG)  |Inglés (NZ)  |Coreano (KO)  |
|Chino (HK)  |Inglés (Reino Unido) |Noruego (NO)  |
|Chino (TW) |Inglés (Estados Unidos) |Polaco (PL)  |
|Chino (ZH) |Finés (FI) |Portugués (BR) |
|Danés (DA)  |Francés (CA)  |Portugués (PT) |
|Neerlandés (NL)   |Francés (FR)  |Ruso (RU) |
|Inglés (AU)  |Alemán (DE) |Español (ES)  |
|Inglés (CA)  |Italiano (IT) |Español (MX)|
|Inglés (IN)  |Japonés (JP) |Sueco (SV)|

El reconocimiento de voz para operadores automáticos está disponible en los siguientes idiomas:
  
|||
|:-----|:-----|
|Chino (ZH)  |Francés (FR)  |
|Inglés (AU)  |Alemán (DE)  |
|Inglés (CA)  |Italiano (IT)  |
|Inglés (IN)  |Japonés (JP)  |
|Inglés (Reino Unido)  |Portugués (BR)  |
|Inglés (Estados Unidos)  |Español (ES)  |
|Francés (CA)   |Español (MX)  |

Los siguientes comandos de voz están disponibles en los catorce (14) idiomas admitidos para el reconocimiento de voz:
  
|Comando de voz| Corresponde a |
|:-----|:-----|
|Sí |Sí (equivale a pulsar 1 para Sí). |
|No |No (equivale a pulsar 2 para No). |
|Repetir |Repite la lista de opciones (equivale a pulsar * para repetir la lista de opciones). |
|Operador |Salida al operador (equivale a pulsar 0 para "Operador"). |
|Menú principal  |Lleva al autor de la llamada al menú principal del operador automático. |
|Cero |Equivale a pulsar 0 (de forma predeterminada, igual que "Operador").|
|Uno |Equivale a pulsar 1. |
|Dos |Equivale a pulsar 2. |
|Tres|Equivale a pulsar 3.|
|Cuatro |Equivale a pulsar 4. |
|Cinco |Equivale a pulsar 5. |
|Seis  |Equivale a pulsar 6. |
|Siete |Equivale a pulsar 7.|
|Ocho |Equivale a pulsar 8.|
|Nueve  |Equivale a pulsar 9.|

### <a name="using-the-operator-option"></a>Usar la opción de operador

Usar el operador para un operador automático es una configuración opcional que proporciona al autor de la llamada una opción para hablar con un operador humano.
  
Tecla 0 y el comando de voz "operador" dirigen la llamada al operador designado de forma predeterminada. Este es el caso de todos los idiomas admitidos para el reconocimiento de voz. También puede usar **las opciones de menú** para establecer un valor personalizado para el operador.
  
El operador puede establecerse en:
  
- Un usuario de Microsoft Teams o un usuario local de Skype empresarial que tenga habilitada la telefonía IP empresarial.
  
- Otro operador automático configurado para su organización.
- Cualquier cola de llamadas que tenga su organización. Para más información sobre las colas de llamadas, consulte [crear una cola de llamadas en la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

### <a name="business-hours-and-call-handling"></a>Horario laboral y administración de llamadas

El horario comercial se establece en cada operador automático. Si no se han establecido las horas de trabajo, todos los días y todas las horas del día se consideran horario comercial porque una programación de 24/7 está establecida de forma predeterminada. El horario comercial se puede establecer con interrupciones en el tiempo durante el día, y todas las horas que no se configuran como horas laborales se consideran horas laborales. Puede establecer distintas opciones de tratamiento de llamadas entrantes y otros saludos (opcionales), y ambos pueden establecerse en horario comercial y fuera de horas.
  
Cada operador automático tiene opciones de control de llamadas que pueden establecerse:
  
- Puede hacer que la llamada se desconecte después del mensaje de saludo.
- También puede:
  - Redirigir la llamada a un usuario de Microsoft teams que tenga una licencia de **sistema telefónico** habilitada para voz empresarial o que tenga asignados planes de llamada. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione una **persona de su empresa** y establezca que las llamadas de esta persona se desvíen de manera automática directamente al correo de voz.

  - Redirigir la llamada a una cola de llamadas. Para más información sobre las colas de llamadas, consulte [crear una cola de llamadas en la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

  - Redirigir la llamada a otro operador automático que haya configurado.
  - Crear opciones de menú y reproducir un mensaje con instrucciones para el autor de la llamada. Por ejemplo: "Pulse 1 para Ventas, pulse 2 para Servicios. Para hablar con el operador, pulse 0 en cualquier momento".

### <a name="menu-options"></a>Opciones de menú

Los operadores automáticos de la nube permiten crear solicitudes de menú ("Presione 1 para las ventas, pulse 2 para servicios") y configure las opciones del menú para enrutar las llamadas según lo que seleccione el usuario. La configuración de opciones de menú para un operador automático permite a una organización proporcionar instrucciones interactivas para que las personas lleguen a su destino con mayor rapidez, sin necesidad de que un operador humano administre las llamadas entrantes. Las indicaciones de menú se pueden crear con texto a voz (mensajes generados por el sistema) o cargando un archivo de audio que se ha grabado. El reconocimiento de voz usa comandos de voz para facilitar la navegación sin entrada manual, pero los autores de llamadas pueden usar también el teclado de su teléfono para navegar por los menús.
  
Las teclas de 0 a 9 se pueden asignar a **las opciones de menú** de un operador automático con el centro de administración de Skype empresarial. Pueden crear conjuntos de opciones de menú diferentes para el horario laboral y el no laboral, y puede activar o desactivar Marcado por nombre en las **opciones del menú**. Se pueden asignar las teclas para transferir las llamadas a:
  
- Un operador, que tiene asignada la tecla 0 de forma predeterminada. Sin embargo, se puede volver a asignar a cualquier otra tecla o quitar del menú.
- Una cola de llamadas.
- Otro operador automático. Los menús de varios niveles se pueden configurar seleccionando una **opción de menú** de un operador automático a otro operador automático con su propio conjunto de opciones de menú, que se denomina "operador automático" anidado ".
- Un usuario de Microsoft teams que tiene una licencia de **sistema telefónico** habilitada para voz empresarial o que tiene planes de llamadas asignados. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione una **persona de su empresa** y establezca que las llamadas de esta persona se desvíen de manera automática directamente al correo de voz.
  
El nombre de cada opción de menú se convierte en una palabra clave de reconocimiento de voz si se ha habilitado el reconocimiento de voz. Por ejemplo, las personas que llamen pueden decir "una" para seleccionar la opción de menú asignada a la clave 1, o simplemente pueden decir "ventas" para seleccionar la misma opción de menú denominada "ventas".
  
Para configurar un operador automático y las opciones de menú, vaya a [configurar un operador automático](create-a-phone-system-auto-attendant.md)de la nube.
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Asignar números de teléfono para un operador automático

Puede asignar un número de servicio de Microsoft, un número de enrutamiento directo o un número híbrido a su operador automático. Consulte [planificar el enrutamiento directo](direct-routing-plan.md) para obtener más información.

Para asignar un número de servicio, necesitará obtener o migrar los números de teléfono de pago o gratuitos existentes. Una vez que recibas los números de teléfono de pago o gratuitos, aparecerán en la <!-- validate nav path --> **** > Los**números de teléfono****de telefonía del** > centro de administración de Skype empresarial y el **tipo de número** que aparece en la lista aparecerán como **servicio-** gratuito. Para obtener sus números de servicio, consulte [obtener números de teléfono de servicio de Skype empresarial y Microsoft Teams](/microsoftteams/getting-service-phone-numbers) , o bien, si desea transferir un número de servicio existente, consulte [transferir números de teléfono a Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener los números de servicio. Para ver cómo hacerlo, vaya a [administrar los números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) .
  
## <a name="related-topics"></a>Temas relacionados

[Esto es lo obtiene con el Sistema telefónico de Office 365](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Ejemplo de pequeña empresa: configurar un operador automático](/microsoftteams/tutorial-org-aa)
