---
title: Operador automático y referencia de marcado de cola de llamadas y reconocimiento de voz
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
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
description: Obtenga información sobre el operador automático y las opciones de marcación de la cola de llamadas y reconocimiento de voz en Teams.
ms.openlocfilehash: 1cb8da2d2e6625de5a1471d1051c1ca51f11bbae
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918966"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Operador automático y referencia de marcado de cola de llamadas y reconocimiento de voz

Marcado por nombre es una característica de un operador automático que también se conoce como búsqueda en directorios. Permite que las personas que llamen a su operador automático usen las respuestas de voz (reconocimiento de voz) o el teclado numérico del teléfono (DTMF) para escribir un nombre completo o parcial en el directorio de la empresa, localizar a la persona y, a continuación, hacer que se le transfiera la llamada. Usted configura el marcado por nombre al configurar la configuración del flujo de [llamadas en un operador automático.](create-a-phone-system-auto-attendant.md#call-flow)

## <a name="searching-for-users"></a>Búsqueda de usuarios

No es necesario que los usuarios que desea localizar y que contacten con el Marcado por nombre tengan un número de teléfono o que tengan asignado un plan de llamadas, pero deben estar Telefonía IP empresarial habilitados para los usuarios de Skype Empresarial **Server.** El marcado por nombre incluso podrá buscar y transferir llamadas a usuarios de Microsoft Teams que se encuentren en diferentes países o regiones para organizaciones nacionales múltiples. Dados los requisitos previos implicados, debe habilitar explícitamente Marcado por nombre en un operador automático.

Marcar por extensión es una característica de un operador automático que también forma parte de la búsqueda en directorios. Permite que las personas que llaman a su operador automático usen las respuestas de voz (reconocimiento de voz) o del teclado del teléfono (DTMF) para que introduzcan la extensión del teléfono del usuario con el que quieren contactar y, a continuación, se les transferirá la llamada. No es necesario que los usuarios a los que desee localizar y localizar con Marcado por extensión tengan un número de teléfono o que tengan asignado un plan de llamadas, pero deben tener Telefonía IP empresarial habilitado para los usuarios de Skype Empresarial **Server.** También necesitará tener un plan de marcado configurado correctamente para los usuarios. El marcado por extensión incluso podrá buscar y transferir llamadas a usuarios de Microsoft Teams que se hospedan en diferentes países o regiones para organizaciones nacionales múltiples. Dados los requisitos previos implicados, debe habilitar explícitamente Marcado por extensión en un operador automático.

### <a name="maximum-directory-size"></a>Tamaño máximo de directorio

No hay límite en el número de usuarios de Active Directory que marcan por nombre y marcado por extensión pueden admitir cuando un autor de llamada busca una persona determinada. El autor de la llamada puede escribir nombres completos o parciales (nombre + apellidos y apellidos + nombre), pero se necesita el número completo de extensión. El tamaño máximo de la lista de nombres que admite un único operador automático mediante el reconocimiento de voz es de 80 000 usuarios.
  
|Tipo de entrada|Formato de búsqueda|Número máximo de usuarios en una organización|
|:-----|:-----|:-----|
|DTMF (entrada con teclado) |Parcial  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre |Sin límite  |
|Voz (entrada de voz) |Nombre  <br/> Apellidos  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre  | 80 000 usuarios |

> [!NOTE]
> Si usa Marcado por nombre con reconocimiento de voz, pero el Active Directory de su organización tiene más de 80 000 usuarios y no ha limitado el ámbito de Marcado por nombre con la característica Ámbito de marcado, Marcado por nombre funcionará para los autores de llamadas con el teclado del teléfono, y la entrada por voz estará disponible para todos los demás escenarios. Puede usar la característica de ámbito de marcado para limitar los nombres que se pueden contactar cambiado el ámbito de Marcado por nombre de un operador automático determinado.
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>Marcado por nombre: entrada mediante teclado (DTMF)
Las personas que llaman pueden usar Marcado por nombre para contactar con los usuarios especificando el nombre completo o parcial de la persona con la que quieren hablar. Hay varios formatos que se pueden usar cuando se introduce el nombre.

Para realizar búsquedas en el directorio de su organización, los usuarios pueden usar la tecla 0 (cero) para indicar un espacio entre el nombre y el apellidos, o viceversa. Cuando escriba el nombre, se les pedirá que finalicen la entrada con el teclado numérico con la tecla #. Por ejemplo, "Después de introducir el nombre de la persona que busca, pulse #". Si se encuentran varios nombres, se proporcionará una lista de nombres al autor de la llamada para que seleccione uno.
  
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

En las búsquedas de personas a través del teclado del teléfono se pueden utilizar diferentes caracteres especiales. Por ejemplo, se le pedirá al usuario que use la tecla de signo de interrogación (#), mientras que la tecla cero (0) se usará para espacios entre nombres. Al pulsar la tecla de asterisco (*) se repetirá la lista de nombres coincidentes.
  
|Carácter especial del teclado del teléfono|Significado|
|:-----|:-----|
|#   |Carácter de fin al introducir un nombre. |
|0   |Espacio entre nombres. |
|*    |Repetir la lista de nombres coincidentes. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Marcado por nombre: reconocimiento de nombres por voz

Los usuarios pueden buscar a otras personas de su organización con su voz (reconocimiento de voz). También pueden contactar con cualquier persona en Active Directory diciendo el nombre completo o parcial de la persona que están intentando localizar. Las entradas de voz pueden reconocer nombres en varios formatos, incluidos Nombre, Apellidos, Nombre + Apellidos o Apellidos + Nombre.
  
Puede habilitar el reconocimiento de voz para un operador automático, pero la entrada con teclado del teléfono (DTMF) no está deshabilitada. La entrada mediante teclado del teléfono se puede usar en cualquier momento incluso si el reconocimiento de voz está activado en el operador automático.
  
Al igual que ocurre con la entrada con teclado del teléfono, si se encuentran varios nombres, la persona que llama escuchará una lista de nombres entre los que seleccionar.
  
Las personas que llaman pueden decir nombres en los siguientes formatos:
  
|Nombre por voz|Tipo de búsqueda|Ejemplo|Resultado de búsqueda|
|:-----|:-----|:-----|:-----|
|Nombre + Apellidos |Completo |Amos Marble |Amos Marble |
|Apellidos + Nombre |Completo  |Marble Amos |Amos Marble |
|Nombre |Completo |Amos |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Amos Jones |
|Apellidos |Completo |Marble |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Ben Marble |
|Nombre o Apellidos |Parcial |Mar |Pulse o diga 1 para Mary Marble  <br/> Pulse o diga 2 para Mary Jones  <br/> Pulse o diga 3 para Amos Marcus |
|Nombre + Apellidos |Parcial |Amos Mar |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Amos Marcus |


> [!NOTE]
> El nombre del nuevo usuario podría tardar hasta 36 horas en aparecer en el directorio de Marcado por nombre con reconocimiento de voz debido al retraso en la replicación de Active Directory.
  
## <a name="language-support"></a>Compatibilidad con idiomas

Los siguientes idiomas están disponibles para texto a voz que se usa con mensajes salientes:
  
|-|-|-|
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
  
|-|-|
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
|Sí | Pulse 1 para Sí. |
|No | Pulse 2 para No. |
|Repetir |Repite la lista de opciones. Presione * en el teclado numérico para repetir la lista de opciones. |
|Operador | Pulse 0 para "Operador" |
|Menú principal  |Lleva al autor de la llamada al menú principal del operador automático. |
|Cero | Presione 0 (de forma predeterminada, igual que "Operador").|
|Uno | Presione 1. |
|Dos | Presione 2. |
|Tres| Presione 3.|
|Cuatro | Presione 4. |
|Cinco | Presione 5. |
|Seis  | Presione 6. |
|Siete | Pulse 7.|
|Ocho |Presione 8.|
|Nueve  |Presione 9.|

## <a name="related-topics"></a>Temas relacionados

[Esto es lo obtiene con el Sistema telefónico](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
