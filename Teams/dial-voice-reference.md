---
title: Operador automático y referencia de marcación de cola de llamadas y reconocimiento de voz
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
description: Obtenga más información sobre las opciones De marcado y reconocimiento de voz del operador automático y de la cola de llamadas en Teams.
ms.openlocfilehash: f62a04735d386637489d52956e6a064a2eba1e4e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098446"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Operador automático y referencia de marcación de cola de llamadas y reconocimiento de voz

Marcar por nombre es una característica de un operador automático que también se conoce como búsqueda de directorios. Permite a las personas que llaman a su operador automático usar respuestas de voz (reconocimiento de voz) o del teclado del teléfono (DTMF) para escribir un nombre completo o parcial para buscar el directorio de la compañía, localizar a la persona y, después, hacer que la llamada se transfiera a ellos. Puede configurar el marcado por nombre al configurar la configuración de flujo de [llamadas en un operador automático.](create-a-phone-system-auto-attendant.md#call-flow)

## <a name="searching-for-users"></a>Buscar usuarios

Los usuarios a los que desea haber localizado y alcanzado con Marcado por nombre no necesitan tener un número de teléfono o tener planes de llamadas asignados, pero deben estar Telefonía IP empresarial habilitados para los usuarios de **Skype Empresarial Server.** Marcar por nombre incluso podrá buscar y transferir llamadas a usuarios de Microsoft Teams hospedados en diferentes países o regiones para organizaciones nacionales. Dados los requisitos previos implicados, se habilita explícitamente Marcar por nombre en un operador automático.

Marcar por extensión es una característica de un operador automático que también forma parte de la búsqueda de directorios. Permite a las personas que llaman a su operador automático usar respuestas de voz (reconocimiento de voz) o del teclado del teléfono (DTMF) para escribir la extensión de teléfono del usuario al que está intentando contactar y, a continuación, hacer que la llamada se les transfiera. Los usuarios a los que desea haber localizado y alcanzado con Marcado por extensión no necesitan tener un número de teléfono o tener planes de llamadas asignados, pero deben estar Telefonía IP empresarial habilitados para los usuarios de **Skype Empresarial Server.** También necesitará tener un plan de marcado configurado correctamente para los usuarios. Marcar por extensión incluso podrá buscar y transferir llamadas a usuarios de Microsoft Teams hospedados en diferentes países o regiones para organizaciones nacionales. Dados los requisitos previos implicados, habilita explícitamente Marcar por extensión en un operador automático.

### <a name="maximum-directory-size"></a>Tamaño máximo de directorio

No hay ningún límite en el número de usuarios de Active Directory Marcado por nombre y Marcado por extensión puede admitir cuando un autor de la llamada busca a una persona específica. Un autor de la llamada puede escribir nombres parciales o completos (Nombre + Apellidos, y también Apellido + Nombre), pero necesita el número de extensión completo. El tamaño máximo de la lista de nombres que un solo operador automático puede admitir con el reconocimiento de voz es de 80 000 usuarios.
  
|Tipo de entrada|Formato de búsqueda|Número máximo de usuarios en una organización|
|:-----|:-----|:-----|
|DTMF (entrada con teclado) |Parcial  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre |Sin límite  |
|Voz (entrada de voz) |Nombre  <br/> Apellidos  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre  | 80 000 usuarios |

> [!NOTE]
> Si usa Marcado por nombre con reconocimiento de voz, pero el Active Directory de su organización es mayor que 80 000 usuarios y no ha limitado el ámbito de Marcado por nombre con la característica Ámbito de marcado, Marcar por nombre seguirá funcionando para los autores de llamadas con un teclado del teléfono y las entradas de voz estarán disponibles para todos los demás escenarios. Puede usar la característica de ámbito de marcado para limitar los nombres que se pueden contactar cambiado el ámbito de Marcado por nombre de un operador automático determinado.
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>Marcado por nombre: entrada mediante teclado (DTMF)
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

### <a name="dial-by-name---name-recognition-with-speech"></a>Marcado por nombre: reconocimiento de nombres por voz

Los usuarios pueden buscar a otras personas de su organización con su voz (reconocimiento de voz). También pueden contactar con cualquier persona de Active Directory diciendo el nombre completo o parcial de la persona a la que están intentando localizar. El uso de entradas de voz puede reconocer nombres en varios formatos, como Nombre, Apellidos, Nombre + Apellidos o Apellidos + Nombre.
  
Puede habilitar el reconocimiento de voz para un operador automático, pero la entrada del teclado del teléfono (DTMF) no está deshabilitada. La entrada del teclado del teléfono se puede usar en cualquier momento, incluso si el reconocimiento de voz está habilitado en el operador automático.
  
Al igual que con la entrada del teclado del teléfono, si se encuentran varios nombres, la persona que llama escuchará una lista de nombres entre los que seleccionar.
  
Las personas que llaman pueden decir nombres en los siguientes formatos:
  
|Nombre con voz|Tipo de búsqueda|Ejemplo|Resultado de búsqueda|
|:-----|:-----|:-----|:-----|
|Nombre + Apellidos |Completo |Amos Marble |Amos Marble |
|Apellidos + Nombre |Completo  |Marble Amos |Amos Marble |
|Nombre |Completo |Amos |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Amos Jones |
|Apellidos |Completo |Marble |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Ben Marble |
|Nombre o Apellidos |Parcial |Mar |Presione o diga 1 para Mary Marble  <br/> Presione o diga 2 para Mary Jones  <br/> Presione o diga 3 para Amós Marco |
|Nombre + Apellidos |Parcial |Amos Mar |Pulse o diga 1 para Amos Marble  <br/> Presione o diga 2 para Amós Marco |


> [!NOTE]
> Un nuevo usuario puede tardar hasta 36 horas en aparecer en el directorio de Marcado por nombre con reconocimiento de voz debido al retraso de replicación de Active Directory.
  
## <a name="language-support"></a>Compatibilidad con idiomas

Los siguientes idiomas están disponibles para texto a voz que se usan con mensajes salientes:
  
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

## <a name="related-topics"></a>Temas relacionados

[Esto es lo obtiene con el Sistema telefónico](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](./getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)