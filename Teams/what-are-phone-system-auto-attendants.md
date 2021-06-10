---
title: ¿Qué son los operadores automáticos en la nube?
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: makolomi
ms.date: 4/2/2019
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre operadores automáticos en la nube y cómo usarlos para permitir que los autores de llamadas se muevan por un sistema de menús para localizar y realizar o transferir llamadas a usuarios o departamentos.
ms.openlocfilehash: c8e5b3f608200036b8c9b9ed5338c558464b32d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100966"
---
# <a name="what-are-cloud-auto-attendants"></a>¿Qué son los operadores automáticos en la nube?

Sistema telefónico proporciona operadores automáticos, que se pueden usar para permitir que los autores de llamadas externos e internos se muevan por un sistema de menús para localizar y realizar o transferir llamadas a usuarios o departamentos de su organización.
  
Un operador automático suele ser un nodo de un sistema, lo que ofrece a un autor de la llamada una serie de mensajes de voz o archivos de audio que escuchan en lugar de un operador humano. Cuando las personas llaman a un número asociado a un operador automático, sus opciones pueden redirigir la llamada a un usuario o localizar a alguien de su organización y, a continuación, conectarse a ese usuario. Pueden expresar sus opciones e interactuar con el sistema de menús mediante un teclado del teléfono (DTMF) o un reconocimiento de voz. Las opciones que realicen también pueden redirigir la llamada a otro operador automático o a una cola de llamadas.
  
Para configurar un operador automático para Sistema telefónico, vaya a Configurar [un operador automático en la nube.](create-a-phone-system-auto-attendant.md)
  
Un operador automático de nube tiene las siguientes características:
  
- Puede transmitir saludos corporativos o informativos.
- Puede proporcionar menús corporativos personalizados. Estos menús se pueden personalizar para que tengan más de un nivel.
- Proporciona una búsqueda de directorio que permite a las personas que llaman a buscar un nombre en el directorio de la organización.
- Permite que alguien que llama llegue o deje un mensaje para una persona de su organización.
- Es compatible con varios idiomas para mensajes, texto a voz y reconocimiento de voz.
- Es compatible con la especificación de días festivos y horas laborables.
- Es compatible con la transferencia de llamadas a un operador, otros usuarios, colas de llamadas y operadores automáticos.
- Es compatible con el correo de voz compartido para que los autores de llamadas dejen un mensaje para una organización.

> [!NOTE]
> Este artículo se aplica tanto a Microsoft Teams como a Skype Empresarial online.

## <a name="getting-started"></a>Introducción

Para comenzar a utilizar operadores automáticos, es importante recordar que:

- Se requiere un operador automático para tener una cuenta de recursos asociada. Vea [Administrar cuentas de recursos en Teams](manage-resource-accounts.md) para obtener más información sobre las cuentas de recursos. <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- Al asignar un número de teléfono a un operador automático, en sentido estricto, lo asigna a la cuenta de recursos asociada con ese operador automático. Esto proporciona una forma de tener acceso a más de un número de teléfono a un operador automático. La mayoría de las veces, una cuenta de recursos usará la licencia gratuita Sistema telefónico de usuario virtual. Esta licencia proporciona Sistema telefónico a los números de teléfono en el nivel organizativo y le permite crear operadores automáticos y colas de llamadas.

> [!NOTE]
> Los números de servicio de enrutamiento directo para operadores automáticos y colas de llamadas solo son compatibles Microsoft Teams usuarios y agentes de llamadas.

   > [!TIP]
   > Para redirigir llamadas a un operador o a una opción de menú que sea un usuario en línea con una licencia de **Sistema telefónico,** deberá habilitar su cuenta para Telefonía IP empresarial o asignarles planes de llamadas. Vea [Asignar Microsoft Teams de complementos.](teams-add-on-licensing/assign-teams-add-on-licenses.md) También puede usar Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obtener y usar números de servicio gratuitos para los operadores automáticos, debe configurar créditos de comunicaciones. Para ello, vea [¿Qué son los créditos de comunicaciones?](what-are-communications-credits.md) y [Configurar créditos de comunicaciones para su organización.](set-up-communications-credits-for-your-organization.md)

    > [!IMPORTANT]
    > Los números de teléfono de usuario (suscriptor) no se pueden asignar a los operadores automáticos; solo se pueden usar números de teléfono de servicio de pago y gratuitos.

- Un sistema de operador automático completo normalmente implicará varios operadores automáticos.
- Es posible aplicar más de un número de teléfono a los operadores automáticos de nivel de entrada.
- Los operadores automáticos que no sean de nivel de entrada o las colas de llamadas en el sistema completo solo necesitarán un número de teléfono si realizarán llamadas RTC salientes.
  
## <a name="feature-overview"></a>Información general sobre características

### <a name="searching-for-users"></a>Buscar usuarios

Marcar por nombre es una característica de un operador automático que también se conoce como búsqueda de directorios. Permite a las personas que llaman a su operador automático usar respuestas de voz (reconocimiento de voz) o del teclado del teléfono (DTMF) para escribir un nombre completo o parcial para buscar el directorio de la compañía, localizar a la persona y, después, hacer que la llamada se transfiera a ellos. Los usuarios a los que desea haber localizado y alcanzado con Marcado por nombre no necesitan tener un número de teléfono o tener planes de llamadas **asignados,** pero deben tener una licencia de Sistema telefónico si son usuarios en línea o Telefonía IP empresarial habilitado para Skype Empresarial Server usuarios. Marcar por nombre incluso podrá buscar y transferir llamadas a Microsoft Teams usuarios hospedados en diferentes países o regiones para organizaciones nacionales múltiples. Dados los requisitos previos implicados, se habilita explícitamente Marcar por nombre en un operador automático.

Marcar por extensión es una característica de un operador automático que también forma parte de la búsqueda de directorios. Permite a las personas que llaman a su operador automático usar respuestas de voz (reconocimiento de voz) o del teclado del teléfono (DTMF) para escribir la extensión de teléfono del usuario al que está intentando contactar y, a continuación, hacer que la llamada se les transfiera. Los usuarios a los que desea haber localizado y alcanzado con Marcado por extensión no necesitan tener un número de teléfono o tener planes de llamadas **asignados,** pero deben tener una licencia de Sistema telefónico si son usuarios en línea o Telefonía IP empresarial habilitado para Skype Empresarial Server usuarios. También necesitará tener un plan de marcado configurado correctamente para los usuarios. Marcar por extensión incluso podrá buscar y transferir llamadas a Microsoft Teams usuarios hospedados en diferentes países o regiones para organizaciones nacionales. Dados los requisitos previos implicados, habilita explícitamente Marcar por extensión en un operador automático.

#### <a name="maximum-directory-size"></a>Tamaño máximo de directorio

No hay ningún límite en el número de usuarios de Active Directory Marcado por nombre y Marcado por extensión puede admitir cuando un autor de la llamada busca a una persona específica. Un autor de la llamada puede escribir nombres parciales o completos (Nombre + Apellidos, y también Apellido + Nombre), pero necesita el número de extensión completo. El tamaño máximo de la lista de nombres que un solo operador automático puede admitir con el reconocimiento de voz es de 80 000 usuarios.
  
|Tipo de entrada|Formato de búsqueda|Número máximo de usuarios en una organización|
|:-----|:-----|:-----|
|DTMF (entrada con teclado) |Parcial  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre |Sin límite  |
|Voz (entrada de voz) |Nombre  <br/> Apellidos  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre  | 80 000 usuarios |

> [!NOTE]
> Si usa Marcado por nombre con reconocimiento de voz, pero el Active Directory de su organización es mayor que 80 000 usuarios y no ha limitado el ámbito de Marcado por nombre con la característica Ámbito de marcado, Marcar por nombre seguirá funcionando para los autores de llamadas con un teclado del teléfono y las entradas de voz estarán disponibles para todos los demás escenarios. Puede usar la característica de ámbito de marcado para limitar los nombres que se pueden contactar cambiado el ámbito de Marcado por nombre de un operador automático determinado.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Marcado por nombre: entrada mediante teclado (DTMF)

Las personas que llamen pueden usar Marcar por nombre para comunicarse con los usuarios especificando el nombre completo o parcial de la persona a la que están intentando contactar. Hay varios formatos que se pueden usar cuando se introduce el nombre.

Para realizar búsquedas en el directorio de su organización, los usuarios pueden usar la tecla 0 (cero) para indicar un espacio entre el nombre y el apellidos, o viceversa. Cuando escriban el nombre, se les pedirá que finalicen la entrada del teclado con la tecla #. Por ejemplo, "Después de introducir el nombre de la persona que busca, pulse #". Si se encuentran varios nombres, se proporcionará una lista de nombres al autor de la llamada para que seleccione uno.
  
Las personas pueden realizar búsquedas por nombre en su organización empleando los siguientes formatos de búsqueda con el teclado del teléfono:
  
|Formato de nombre|Tipo de búsqueda|Ejemplo|Resultado de búsqueda|
|:-----|:-----|:-----|:-----|
|Nombre + Apellidos |Completo  |Amos0Marble# |Amos Marble |
|Apellidos + Nombre |Completo |Marble0Amos#  |Amos Marble |
|Nombre  |Completo   |Amos#   |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus |
|Apellidos |Completo |Marble#  |Pulse 1 para Amos Marble  <br/> Pulse 2 para Mary Marble |
|Nombre o Apellidos |Parcial |Mar# |Pulse 1 para Mary Marble  <br/> Pulse 2 para Mary Jones  <br/> Pulse 3 para Amos Marcus |
|Nombre + Apellidos |Parcial |Amos0Mar # |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus |
|Apellidos + Nombre |Parcial |Mar0Am# |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus |

En las búsquedas de personas a través del teclado del teléfono se pueden utilizar diferentes caracteres especiales. Por ejemplo, se le pedirá a la persona que use la tecla de libra (#), mientras que la tecla cero (0) se usa para un espacio entre nombres. Al pulsar la tecla de asterisco (*) se repetirá la lista de nombres coincidentes.
  
|Carácter especial del teclado del teléfono|Significado|
|:-----|:-----|
|#   |Carácter de fin al introducir un nombre. |
|0   |Espacio entre nombres. |
|*    |Repetir la lista de nombres coincidentes. |

#### <a name="dial-by-name---name-recognition-with-speech"></a>Marcado por nombre: reconocimiento de nombres por voz

Los usuarios pueden buscar a otras personas de su organización con su voz (reconocimiento de voz). También pueden contactar con cualquier persona de Active Directory diciendo el nombre de la persona a la que están intentando localizar. El uso de entradas de voz puede reconocer nombres en varios formatos, como Nombre, Apellidos, Nombre + Apellidos o Apellidos + Nombre.
  
Puede habilitar el reconocimiento de voz para un operador automático, pero la entrada del teclado del teléfono (DTMF) no está deshabilitada. Teléfono entrada del teclado numérico se puede usar en cualquier momento, incluso si el reconocimiento de voz está habilitado en el operador automático.
  
Al igual que con la entrada del teclado del teléfono, si se encuentran varios nombres, la persona que llama escuchará una lista de nombres entre los que seleccionar.
  
Las personas que llaman pueden decir nombres en los siguientes formatos:
  
|Nombre con voz|Tipo de búsqueda|Ejemplo|Resultado de búsqueda|
|:-----|:-----|:-----|:-----|
|Nombre + Apellidos |Completo |Amos Marble |Amos Marble |
|Apellidos + Nombre |Completo  |Marble Amos |Amos Marble |
|Nombre |Completo |Amos |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Amos Jones |
|Apellidos |Completo |Marble |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Ben Marble |

> [!NOTE]
> Un nuevo usuario puede tardar hasta 36 horas en aparecer en el directorio de Marcado por nombre con reconocimiento de voz debido al retraso de replicación de Active Directory.
  
### <a name="language-support"></a>Compatibilidad con idiomas

Los siguientes idiomas están disponibles para texto a voz que se usan con mensajes salientes:
  
|A-E|E-J|K-Z|
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

La entrada de reconocimiento de voz para operadores automáticos está disponible en los siguientes idiomas:
  
|A-F|F-Z|
|:-----|:-----|
|Chino (ZH)  |Francés (FR)  |
|Inglés (AU)  |Alemán (DE)  |
|Inglés (CA)  |Italiano (IT)  |
|Inglés (IN)  |Japonés (JP)  |
|Inglés (Reino Unido)  |Portugués (BR)  |
|Inglés (Estados Unidos)  |Español (ES)  |
|Francés (CA)   |Español (MX)  |

Los siguientes comandos de voz están disponibles en los 14 idiomas admitidos para el reconocimiento de voz:
  
|Comando de voz| Corresponde a |
|:-----|:-----|
|Sí | Presione 1 para Sí. |
|No | Presione 2 para No. |
|Repetir |Repite la lista de opciones. Presione * en el teclado numérico para repetir la lista de opciones. |
|Operador | Presione 0 para "Operador" |
|Menú principal  |Lleva al autor de la llamada al menú principal del operador automático. |
|Cero | Presione 0 (de forma predeterminada, igual que "Operador").|
|Uno | Presione 1. |
|Dos | Presione 2. |
|Tres| Presione 3.|
|Cuatro | Presione 4. |
|Cinco | Presione 5. |
|Seis  | Presione 6. |
|Siete | Presione 7.|
|Ocho |Presione 8.|
|Nueve  |Presione 9.|

### <a name="the-operator-option"></a>La opción de operador

Opcionalmente, se puede configurar un operador automático para que un autor de la llamada pueda seleccionarlo para que hable con un operador humano.
  
La tecla 0 y el comando de voz "Operador" dirigen la llamada al operador designado de forma predeterminada. Este es el caso de todos los idiomas admitidos para el reconocimiento de voz. También puede usar Establecer **opciones del menú** para establecer un valor personalizado para el operador.
  
El operador se puede establecer en:
  
- Un Microsoft Teams o un Skype Empresarial Server que está Telefonía IP empresarial habilitado.
- Otro operador automático configurado para su organización.
- Cualquier cola de llamadas que tenga su organización. Para obtener más información sobre las colas de llamadas, vea [Crear una cola de llamadas en la nube.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

### <a name="business-hours-and-call-handling"></a>Horario laboral y administración de llamadas

El horario laboral se puede establecer en cada operador automático. Si el horario laboral no está establecido, todos los días y todas las horas del día se consideran horario laboral porque una programación 24/7 está establecida de forma predeterminada. El horario laboral se puede establecer con descansos en el tiempo durante el día y todas las horas que no se establecen como horas laborables se consideran fuera del horario laboral. Puede establecer diferentes opciones de administración de llamadas entrantes y saludos diferentes (que son opcionales) para horas laborables y adicionales.
  
Cada operador automático tiene varias opciones posibles de administración de llamadas:
  
- La llamada puede desconectarse después de reproducir un saludo.
- También puede:
  - Redirigir la llamada a un usuario Microsoft Teams  que tenga una licencia de Sistema telefónico habilitada para Telefonía IP empresarial o que tenga planes de llamadas asignados. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione una **persona de su empresa** y establezca que las llamadas de esta persona se desvíen de manera automática directamente al correo de voz.

  - Redirigir la llamada a una cola de llamadas. Para obtener más información sobre las colas de llamadas, vea [Crear una cola de llamadas en la nube.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

  - Redirigir la llamada a otro operador automático.

El operador automático expresa estas opciones al autor de la llamada cuando reproduce las indicaciones del menú. Por ejemplo: "Pulse 1 para Ventas, pulse 2 para Servicios. Para hablar con el operador, pulse 0 en cualquier momento".

### <a name="set-menu-options"></a>Opciones del menú Establecer

Los operadores automáticos en la nube le permiten crear mensajes de menú ("Presione 1 para ventas, presione 2 para servicios") y configurar opciones de menú para enrutar llamadas en función de las selecciones de usuario. Las opciones de menú para un operador automático permiten a una organización proporcionar una serie de opciones que guían a los autores de llamadas a su destino más rápido, sin depender de un operador humano para controlar las llamadas entrantes. Las solicitudes de menú se pueden crear mediante texto a voz (mensajes generados por el sistema) o cargando un archivo de audio grabado. El reconocimiento de voz acepta comandos de voz para la navegación manos libres, pero las personas que llaman también pueden usar el teclado del teléfono para navegar por los menús.
  
Las teclas del 0 al 9 se pueden asignar a las teclas de marcado de un operador automático mediante el centro Skype Empresarial administración. Pueden crear conjuntos de opciones de menú diferentes para el horario laboral y el no laboral, y puede activar o desactivar Marcado por nombre en las **opciones del menú**. Se pueden asignar las teclas para transferir las llamadas a:
  
- Un operador, que tiene asignada la tecla 0 de forma predeterminada. Sin embargo, se puede reasignar a cualquier otra clave o quitarla del menú.
- Una cola de llamadas.
- Otro operador automático. Los menús de varios niveles se  pueden configurar señalando una opción de menú en un operador automático a otro operador automático con su propio conjunto de opciones de menú, que se denomina operador automático "anidado".
- Un Microsoft Teams usuario que tiene una **Sistema telefónico** que está Telefonía IP empresarial habilitada o tiene planes de llamadas asignados. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione una **persona de su empresa** y establezca que las llamadas de esta persona se desvíen de manera automática directamente al correo de voz.
  
El nombre de cada opción de menú se convierte en una palabra clave de reconocimiento de voz si se ha habilitado el reconocimiento de voz. Por ejemplo, los autores de llamadas pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1, o pueden decir "Ventas" para seleccionar la misma opción de menú denominada "Ventas".
  
Para configurar un operador automático y las opciones de menú, vaya [a Configurar un operador automático en la nube.](create-a-phone-system-auto-attendant.md)
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Asignar números de teléfono para un operador automático

Puede asignar un número de servicio de Microsoft, un número de enrutamiento directo o un número híbrido a la cuenta de recursos vinculado del operador automático (o a varias cuentas de recursos si se desea más de un número de teléfono). Vea [Planear enrutamiento directo para](direct-routing-plan.md) obtener más información.

Para asignar un número de servicio, deberá obtener o portabilidad los números de servicio gratuitos o de pago existentes. Una vez que reciba los números de teléfono gratuitos o gratuitos, se mostrarán en Skype Empresarial centro de administración de Teléfono  >    >  **números.** **El tipo de** número se muestra **como Servicio gratuito.** Para obtener los números de servicio, vea Obtener números de teléfono de servicio para Skype Empresarial y [Microsoft Teams](./getting-service-phone-numbers.md) o, si desea transferir y el número de servicio existente, vea Transferir números de teléfono a [Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
  
> [!NOTE]
> Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener números de servicio. Vaya [a Administrar números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo.
  
## <a name="related-topics"></a>Temas relacionados

[Esto es lo obtiene con el Sistema telefónico](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](./getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)