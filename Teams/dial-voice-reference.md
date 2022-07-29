---
title: Referencia de marcado y reconocimiento de voz del operador automático y de la cola de llamadas
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Obtenga información sobre las opciones De marcado automático y cola de llamadas y reconocimiento de voz en Teams.
ms.openlocfilehash: 93a20be62f09ed7b636c593ecac48927d70e237f
ms.sourcegitcommit: 55ba3ed53421da6619724a360d15e80262241079
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "67070731"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Referencia de marcado y reconocimiento de voz del operador automático y de la cola de llamadas

Marcado por nombre o extensión es una característica de operador automático que permite a los autores de llamadas ponerse en contacto con los usuarios de Teams de su organización. Con la voz o el teclado del teléfono, los autores de llamadas pueden decir o escribir el nombre completo o parcial, o la extensión de la persona con la que quieran ponerse en contacto. El operador automático buscará en el directorio de la compañía, localizará a la persona y, a continuación, transferirá el autor de la llamada a esa persona.  Marcado por nombre o Marcado por extensión son las opciones que configura al [configurar las opciones de flujo de llamadas en un operador automático](create-a-phone-system-auto-attendant.md?tabs=call-flow).

## <a name="searching-for-users"></a>Búsqueda de usuarios

No es necesario que los usuarios de Teams a los que se les pueda contactar mediante marcado por nombre **tengan un número de teléfono o que tengan asignados planes de llamadas, pero deben estar Telefonía IP empresarial habilitados para los usuarios de Skype Empresarial Server**. Para las organizaciones multinacionales, Marcado por nombre buscará y transferirá los autores de llamadas a los usuarios de Microsoft Teams que se encuentren en diferentes países o regiones.

No es necesario que los usuarios de Teams a los que se les pueda contactar mediante marcado por extensión **tengan un número de teléfono o que tengan asignados planes de llamadas, pero deben estar Telefonía IP empresarial habilitados para los usuarios de Skype Empresarial Server**. También necesitará tener un plan de marcado configurado adecuadamente para los usuarios. Para organizaciones multinacionales, Marcado por extensión buscará y transferirá los autores de llamadas a los usuarios de Microsoft Teams que se encuentren en diferentes países o regiones.

Dados los requisitos previos implicados, el marcado por nombre o extensión debe habilitarse explícitamente al configurar un operador automático.

### <a name="maximum-directory-size"></a>Tamaño máximo de directorio

No hay límite en el número de usuarios de Active Directory marcado por nombre y marcado por extensión puede admitir cuando una persona busca una persona específica. El autor de la llamada puede escribir nombres completos o parciales (Nombre + Apellidos, y también Apellidos + Nombre), pero necesita el número de extensión completo. El tamaño máximo de lista de nombres que admite un único operador automático mediante el reconocimiento de voz es de 80 000 usuarios.
  
|Tipo de entrada|Formato de búsqueda|Número máximo de usuarios en una organización|
|:-----|:-----|:-----|
|DTMF (entrada con teclado) |Parcial  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre |Sin límite  |
|Voz (entrada de voz) |Apellido  <br/> Apellido  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre  | 80 000 usuarios |

> [!NOTE]
> Si usa Marcado por nombre con reconocimiento de voz, pero el Active Directory de su organización tiene más de 80 000 usuarios y no ha limitado el ámbito de Marcado por nombre mediante la característica [Ámbito](create-a-phone-system-auto-attendant.md?tabs=dial-scope) de marcado, Marcado por nombre seguirá funcionando para los autores de llamadas con el teclado del teléfono y las entradas de voz estarán disponibles para todos los demás escenarios. Puede usar la característica de ámbito de marcado para limitar los nombres que se pueden contactar cambiado el ámbito de Marcado por nombre de un operador automático determinado.

### <a name="search-considerations"></a>Consideraciones de búsqueda

Marcado por nombre busca primero en el directorio de toda la organización antes de aplicar las listas Incluir o Excluir ámbito de marcado que se han configurado. Si la búsqueda inicial en todo el directorio devuelve más de 100 usuarios, no se aplicarán las listas de ámbito de marcado, se producirá un error en la búsqueda y al autor de la llamada se le notificará que se encontraron demasiados nombres.

## <a name="dial-by-name---keypad-dtmf-entry"></a>Marcado por nombre: entrada mediante teclado (DTMF)

Los autores de llamadas pueden usar Marcado por nombre para ponerse en contacto con los usuarios especificando el nombre completo o parcial de la persona con la que intentan ponerse en contacto. Hay varios formatos que se pueden usar cuando se escribe el nombre.

Para realizar búsquedas en el directorio de su organización, los usuarios pueden usar la tecla 0 (cero) para indicar un espacio entre el nombre y el apellidos, o viceversa. Cuando escriba el nombre, se le pedirá que termine la entrada con el teclado numérico con la tecla #. Por ejemplo, "Después de introducir el nombre de la persona que busca, pulse #". Si se encuentran varios nombres, se proporcionará una lista de nombres al autor de la llamada para que seleccione uno.

> [!NOTE]
> Si quedan más de 5 nombres después de aplicar las listas Incluir o Excluir ámbito de marcado, se producirá un error en la búsqueda y al autor de la llamada se le notificará que se encontraron demasiados nombres.
  
Las personas pueden realizar búsquedas por nombre en su organización empleando los siguientes formatos de búsqueda con el teclado del teléfono:
  
|Formato de nombre|Tipo de búsqueda|Ejemplo|Resultado de búsqueda|
|:-----|:-----|:-----|:-----|
|Nombre + Apellidos |Completo  |Amos0Marble# |Amos Marble |
|Apellidos + Nombre |Completo |Marble0Amos#  |Amos Marble |
|Apellido  |Completo   |Amos#   |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus |
|Apellido |Completo |Marble#  |Pulse 1 para Amos Marble  <br/> Pulse 2 para Mary Marble |
|Nombre o Apellidos |Parcial |Mar# |Pulse 1 para Mary Marble  <br/> Pulse 2 para Mary Jones  <br/> Pulse 3 para Amos Marcus |
|Nombre + Apellidos |Parcial |Amos0Mar # |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus |
|Apellidos + Nombre |Parcial |Mar0Am# |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus |

En las búsquedas de personas a través del teclado del teléfono se pueden utilizar diferentes caracteres especiales. Por ejemplo, se le pedirá al contacto que use la tecla de almohadilla (#), mientras que la tecla cero (0) se usa para un espacio entre nombres. Al pulsar la tecla de asterisco (*) se repetirá la lista de nombres coincidentes.
  
|Carácter especial del teclado del teléfono|Significado|
|:-----|:-----|
|#   |Carácter de fin al introducir un nombre. |
|0   |Espacio entre nombres. |
|*    |Repetir la lista de nombres coincidentes. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Marcado por nombre: reconocimiento de nombres por voz

Las personas pueden buscar a otros usuarios de su organización con su voz (reconocimiento de voz). También pueden ponerse en contacto con cualquier persona de Active Directory diciendo el nombre completo o parcial de la persona a la que están intentando localizar. El uso de entradas de voz puede reconocer nombres en varios formatos, como Nombre, Apellidos, Nombre + Apellidos o Apellidos + Nombre.
  
Puede habilitar el reconocimiento de voz para un operador automático, pero la entrada mediante teclado del teléfono (DTMF) no está deshabilitada. La entrada mediante teclado del teléfono puede usarse en cualquier momento incluso si el reconocimiento de voz está habilitado en el operador automático.
  
Al igual que con la entrada del teclado del teléfono, si se encuentran varios nombres, la persona que llama escuchará una lista de nombres entre los que seleccionar.

> [!NOTE]
> Si quedan más de 5 nombres después de aplicar las listas Incluir o Excluir ámbito de marcado, se producirá un error en la búsqueda y al autor de la llamada se le notificará que se encontraron demasiados nombres.
  
Los autores de llamadas pueden decir los nombres en los siguientes formatos:
  
|Nombre con voz|Tipo de búsqueda|Ejemplo|Resultado de búsqueda|
|:-----|:-----|:-----|:-----|
|Nombre + Apellidos |Completo |Amos Marble |Amos Marble |
|Apellidos + Nombre |Completo  |Marble Amos |Amos Marble |
|Apellido |Completo |Amos |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Amos Jones |
|Apellido |Completo |Marble |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Ben Marble |
|Nombre o Apellidos |Parcial |Marzo |Pulse o diga 1 para Mary Marble  <br/> Pulse o diga 2 para Mary Jones  <br/> Presiona o di 3 para Amos Marcus |
|Nombre + Apellidos |Parcial |Amos Mar |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Amos Marcus |

> [!NOTE]
> Un nuevo usuario puede tardar hasta 36 horas en aparecer su nombre en el directorio de Marcado por nombre con reconocimiento de voz debido al retraso de replicación de Active Directory.

### <a name="dial-by-extension"></a>Marcar por extensión

Los usuarios que quiera que estén disponibles para **Marcado por extensión** deben tener una extensión especificada como parte de uno de los siguientes atributos del teléfono definidos en Active Directory (y sincronizados a través de Azure AD Connect) o Azure Active Directory. (Vea [Agregar usuarios individualmente o de forma masiva](/microsoft-365/admin/add-users/add-users) para obtener más información).

- TelephoneNumber (AD y Azure AD)
- HomePhone (AD)
- Dispositivos móviles (AD y Azure AD)
- OtherTelephone (AD)

El formato necesario para introducir la extensión en el campo de número de teléfono de usuario puede ser uno de los siguientes formatos:

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- Ejemplo 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- Ejemplo 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"
- Ejemplo 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

Puede establecer la extensión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com/) o en el [Centro de administración de Azure Active Directory](https://aad.portal.azure.com). Pueden pasar hasta 12 horas antes de que los cambios estén disponibles para los operadores automáticos y las colas de llamadas.

> [!NOTE]
>  Si usa el campo TelephoneNumber para definir la extensión, Microsoft recomienda que use el formato *+\<phone number>;ext=\<extension>*. Si al usuario también se le asigna un número de teléfono de Teams, debe definir ambos números de la misma manera.


## <a name="language-support"></a>Compatibilidad con idiomas

La compatibilidad con idiomas para texto a voz y reconocimiento de voz está disponible en estos [idiomas admitidos](create-a-phone-system-auto-attendant-languages.md).

Los siguientes comandos de voz están disponibles para el reconocimiento de voz:
  
|Comando de voz| Corresponde a |
|:-----|:-----|
|Sí | Presiona 1 para Sí. |
|No | Presione 2 para No. |
|Repetir |Repite la lista de opciones. Presiona * en el teclado numérico para repetir la lista de opciones. |
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

[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](./getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
