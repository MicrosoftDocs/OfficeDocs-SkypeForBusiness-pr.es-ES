---
title: Operador automático y referencia de la cola de llamadas y reconocimiento de voz
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
description: Obtenga más información sobre las opciones de reconocimiento de voz y el operador automático en la cola de llamadas de Teams.
ms.openlocfilehash: bf520fa4dffe258da523c8815449f1e71279d7f2
ms.sourcegitcommit: bc471f18e40e37456edc9696e11b175581847617
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2020
ms.locfileid: "48800573"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Operador automático y referencia de la cola de llamadas y reconocimiento de voz

El marcado por nombre es una característica de un operador automático que también se conoce como búsqueda de directorio. Permite que las personas que llaman a su operador automático usen la voz (reconocimiento de voz) o las respuestas del teclado (DTMF) para escribir un nombre completo o parcial para buscar en el directorio de la empresa, ubicar a la persona y, a continuación, transferir la llamada. Configure el marcado por nombre al [configurar la configuración del flujo de llamadas en un operador automático](create-a-phone-system-auto-attendant.md#call-flow).

## <a name="searching-for-users"></a>Buscar usuarios

No es necesario que los usuarios que desean encontrarse con el método de marcado por nombre **tengan un número de teléfono o tengan asignados planes de llamadas, pero deben tener una licencia de sistema telefónico si se trata de usuarios en línea o habilitar Enterprise Voice para usuarios de Skype empresarial Server** . Es posible que el marcado por nombre pueda buscar y transferir llamadas a los usuarios de Microsoft teams que se hospedan en diferentes países o regiones para organizaciones multinacionales. Dados los requisitos previos implicados, habilita explícitamente el marcado por nombre en un operador automático.

La extensión de marcado es una característica de un operador automático que también forma parte de la búsqueda en directorios. Permite a las personas que llaman a su operador automático usar voz (reconocimiento de voz) o sus respuestas de teclado (DTMF) del teléfono para introducir la extensión de teléfono del usuario al que está intentando acceder y, a continuación, se les transfiere la llamada. Los usuarios que desee que se encuentren y que tengan acceso telefónico por extensión  **no necesitan tener un número de teléfono o tener planes de llamadas asignados, pero deben tener una licencia de sistema telefónico si son usuarios conectados o habilitado para usar Enterprise Voice para usuarios de Skype empresarial Server** . También necesitará tener un plan de marcado adecuado para sus usuarios. La opción de marcado por extensión podrá buscar y transferir llamadas a los usuarios de Microsoft teams que estén hospedados en diferentes países o regiones para organizaciones multinacionales. Dados los requisitos previos implicados, habilita de forma explícita la función de marcado por extensión en un operador automático.

### <a name="maximum-directory-size"></a>Tamaño máximo de directorio

No hay ningún límite en el número de usuarios de Active Directory marcado por nombre y la extensión de marcado puede admitir cuando una persona que llama busca una persona determinada. Una persona que llama puede escribir nombres parciales o completos (nombre + apellido, y también Apellidos + nombre), pero necesita el número de extensión completo. El tamaño de la lista de nombres máximo que un solo operador automático puede admitir con el reconocimiento de voz es de 80.000 usuarios.
  
|Tipo de entrada|Formato de búsqueda|Número máximo de usuarios en una organización|
|:-----|:-----|:-----|
|DTMF (entrada con teclado) |Parcial  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre |Sin límite  |
|Voz (entrada de voz) |FirstName  <br/> Apellidos  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre  | 80.000 usuarios |

> [!NOTE]
> Si usa el marcado por nombre con reconocimiento de voz, pero el directorio activo de su organización es superior a 80.000 usuarios y no se ha limitado el ámbito de marcado por nombre con la característica de ámbito de marcado, el marcado por nombre seguirá funcionando con las personas que llamen con el teclado del teléfono, y las entradas de voz estarán disponibles para todos los demás escenarios. Puede usar la característica de ámbito de marcado para limitar los nombres que se pueden contactar cambiado el ámbito de Marcado por nombre de un operador automático determinado.
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>Marcado por nombre: entrada mediante teclado (DTMF)
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
|Nombre + Apellidos |Parcial |Amos0Mar # |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus |
|Apellidos + Nombre |Parcial |Mar0Am# |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus |

En las búsquedas de personas a través del teclado del teléfono se pueden utilizar diferentes caracteres especiales. Por ejemplo, se le solicitará a la persona que use la tecla almohadilla (#), mientras que la tecla cero (0) se usa para un espacio entre nombres. Al pulsar la tecla de asterisco (*) se repetirá la lista de nombres coincidentes.
  
|Carácter especial del teclado del teléfono|Significado|
|:-----|:-----|
|#   |Carácter de fin al introducir un nombre. |
|,0   |Espacio entre nombres. |
|*    |Repetir la lista de nombres coincidentes. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Marcado por nombre: reconocimiento de nombres por voz

Los usuarios pueden buscar otras personas en su organización con su voz (reconocimiento de voz). También pueden comunicarse con cualquier persona en Active Directory diciendo el nombre de la persona que está tratando de ubicar. El uso de entradas de voz puede reconocer nombres en varios formatos, como FirstName, LastName, FirstName + LastName o LastName + Name.
  
Puede habilitar el reconocimiento de voz para un operador automático, pero la entrada del teclado (DTMF) no está deshabilitada. La entrada del teclado del teléfono se puede usar en cualquier momento incluso si el reconocimiento de voz está habilitado en el operador automático.
  
Al igual que con la entrada del teclado del teléfono, si se encuentran varios nombres, la persona que llama escucha una lista de nombres para seleccionar.
  
Las personas que llaman pueden decir nombres en los siguientes formatos:
  
|Nombre con voz|Tipo de búsqueda|Ejemplo|Resultado de búsqueda|
|:-----|:-----|:-----|:-----|
|Nombre + Apellidos |Completo |Amos Marble |Amos Marble |
|Apellidos + Nombre |Completo  |Marble Amos |Amos Marble |
|FirstName |Completo |Amos |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Amos Jones |
|Apellidos |Completo |Marble |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Ben Marble |

> [!NOTE]
> Es posible que tarde hasta 36 horas para que un nuevo usuario tenga su nombre en el directorio de marcado por nombre con reconocimiento de voz debido al retraso de replicación de Active Directory.
  
## <a name="language-support"></a>Compatibilidad con idiomas

Los siguientes idiomas están disponibles para el texto a voz que se usa con indicaciones salientes:
  
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

La entrada de reconocimiento de voz para los operadores automáticos está disponible en los siguientes idiomas:
  
|||
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
|Sí | Pulse 1 para sí. |
|No | Pulse 2 para no. |
|Repetir |Repite la lista de opciones. Presione * en el teclado numérico para repetir la lista de opciones. |
|Operador | Pulse 0 para "operador" |
|Menú principal  |Lleva al autor de la llamada al menú principal del operador automático. |
|Cero | Pulse 0 (de forma predeterminada, igual que "operador").|
|Uno | Presione 1. |
|Dos | Pulsa 2. |
|Tres| Pulse 3.|
|Cuatro | Pulse 4. |
|Cinco | Pulse 5. |
|Seis  | Presione 6. |
|Siete | Presione 7.|
|Ocho |Pulse 8.|
|Nueve  |Presione 9.|

## <a name="related-topics"></a>Temas relacionados

[Esto es lo obtiene con el Sistema telefónico](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Ejemplo de pequeña empresa: configurar un operador automático](/microsoftteams/tutorial-org-aa)
