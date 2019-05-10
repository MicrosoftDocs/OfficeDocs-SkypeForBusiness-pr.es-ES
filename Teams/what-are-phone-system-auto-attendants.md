---
title: ¿Cuáles son los operadores automáticos de la nube?
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.autoattendants.overview
ms.custom:
- Phone System
description: Obtenga información sobre qué son los operadores automáticos en la nube y cómo usarlas.
ms.openlocfilehash: 4ab2ffd0803df57db437e2597db9a95b44d9be75
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865151"
---
# <a name="what-are-cloud-auto-attendants"></a>¿Cuáles son los operadores automáticos de la nube?

Sistema telefónico en Office 365 proporciona a operadores automáticos, que se pueden usar para permitir que externo y mover los autores de llamadas internas a través de un sistema de menús para localizar y colocar o transferir las llamadas a los usuarios de la compañía o los departamentos de la organización.
  
Un operador automático es una serie de mensajes de voz o los archivos de audio que escuchen los autores de llamadas en lugar de un operador humano cuando llaman a una organización. Cuando las personas llaman a un número asociado a un operador automático, sus opciones pueden redirigir la llamada a un usuario o busque a alguien en su organización y, a continuación, conectarse a ese usuario. Puede express sus opciones e interactuar con el sistema de menús mediante el uso de un teclado de teléfono (DTMF) o el reconocimiento de voz.
  
Para configurar un operador automático para el sistema telefónico en Office 365, vaya a [configurar un operador automático de la nube](create-a-phone-system-auto-attendant.md).
  
Un operador automático de la nube tiene las siguientes características:
  
- Puede transmitir saludos corporativos o informativos.
- Puede proporcionar menús corporativos personalizados. Estos menús se pueden personalizar para que tengan más de un nivel.
- Proporciona búsqueda en el directorio que permite a las personas que llaman al buscar en el directorio de la organización para un nombre.
- Permite que una persona que llama en para llegar a o dejar un mensaje para una persona de su organización.
- Admite varios idiomas para los mensajes de voz, texto a voz y reconocimiento de voz.
- Admite cómo especificar los días festivos y horario.
- Admite la transferencia de llamada a un operador, otros usuarios, las colas de llamadas y operadores automáticos.

> [!NOTE]
> En este artículo se aplica a Microsoft Teams y Skype para profesionales en línea.

## <a name="getting-started"></a>Introducción

Para comenzar a utilizar operadores automáticos, es importante recordar que:

- Un operador automático es necesario tener una cuenta de recurso asociado. Para obtener información detallada sobre las cuentas de recursos, vea [Administrar cuentas de recursos en los equipos](manage-resource-accounts.md) .
- Si tiene previsto asignar un número de enrutamiento directa, debe adquirir y asignar las siguientes licencias para las cuentas de recursos \(Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico\).
- Si se asigna un número de servicio de Microsoft en su lugar, debe adquirir y asignar las licencias siguientes a la cuenta del recurso \(Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico y un Plan de llamar a\).
- Sólo debe obtener licencia para las cuentas de recursos con un número de teléfono que se les haya asignado. En una cola de llamada o de operador automático anidados, no es necesario para el resto de los operadores automáticos de licencia o colas de llamadas si no tienen números de teléfono asociados con ellos. 

> [!NOTE]
> Números de servicio de enrutamiento directos para colas de operador y llamada automático se admiten para los usuarios de Microsoft Teams y sólo los agentes.

> [!NOTE]
> Microsoft está trabajando en un modelo de licencias adecuado para aplicaciones como automáticos en la nube y las colas de llamadas, para ahora tiene que usar el modelo de licencias de usuario.
    
   > [!TIP]
   > Para redirigir las llamadas a un operador o una opción de menú que es un usuario con una licencia de **Sistema telefónico** en línea, debe habilitarlos para Enterprise Voice o asignar planes de llamada a ellos. Vea [las licencias de asignar los equipos de Microsoft](assign-teams-licenses.md). También puede usar Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obtener y usar números de servicio gratuito para los operadores automáticos, debe configurar Communications créditos. Para hacer esto, vea [¿Cuáles son las comunicaciones créditos?](what-are-communications-credits.md) y [Configurar Communications créditos para su organización](set-up-communications-credits-for-your-organization.md).

    > [!IMPORTANT]
    > Los números de teléfono de usuario (suscriptor) no se pueden asignar a los operadores automáticos; solo se pueden usar números de teléfono de servicio de pago y gratuitos.

- Un sistema de operador automático completa por lo general requerirá varios operadores automáticos y sólo se requiere un número de teléfono asignado único para el automático de nivel superior o de entrada de operador. Otros operadores automáticos o colas de llamadas en todo el sistema sólo necesita un número de teléfono si desea proporcionar varios puntos de entrada en el sistema.
- Es posible aplicar más de un número de teléfono a un operador automático mediante la asociación de más de una cuenta de recurso a un operador automático.
  
## <a name="feature-overview"></a>Información general de características

### <a name="dial-by-name"></a>Marcado por nombre

Marcado por nombre es una característica de un operador automático que también se conoce como búsqueda en el directorio. Permite a las personas que llame a su operador automático para utilizar voz (reconocimiento de voz) o sus respuestas de teclado (DTMF) teléfono para escribir un nombre completo o parcial para buscar en el directorio de la compañía, busque a la persona y, a continuación, haga transferir la llamada a ellos. Los usuarios que desea tener que se encuentra y alcanzar mediante marcado por nombre de **no es necesario tener un número de teléfono o llamar a planes asignados a ellos, pero deben tener una licencia de sistema telefónico si son usuarios en línea o EV habilitado para local a los usuarios**. Marcado por nombre incluso podrán buscar y transferir las llamadas a los usuarios de Microsoft Teams que se hospedan en distintos países o regiones para las organizaciones multinacionales.

### <a name="maximum-directory-size"></a>Tamaño máximo de directorio

No hay ningún límite en el tamaño de Active Directory para el que se admite marcado por nombre cuando se usa el teclado de teléfono para buscar para escribir nombres parciales o completos (FirstName + LastName (apellidos) y también LastName (apellidos) + FirstName). Sin embargo, el tamaño de la lista Nombre máximo que un operador automático solo puede admite el uso de reconocimiento de nombre con voz es 80.000 usuarios.
  
|Tipo de entrada|Formato de búsqueda|Número máximo de usuarios en una organización|
|:-----|:-----|:-----|
|DTMF (entrada con teclado) |Parcial  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre |Sin límite  |
|Voz (entrada de voz) |FirstName  <br/> LastName (apellidos)  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre  | 80.000 usuarios |

> [!NOTE]
> Si usa marcado por nombre con voz es superior a 80.000 usuarios reconocimiento de voz, pero de Active Directory la organización y que no ha limitado el ámbito de marcado por nombre mediante la característica de ámbito de marcado, seguirán funcionando para los llamadores con un teclado de teléfono marcado por nombre , y las entradas de voz estará disponibles para todos los demás escenarios. Puede usar la característica de ámbito de marcado para limitar los nombres que se pueden contactar cambiado el ámbito de Marcado por nombre de un operador automático determinado.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Marcado por nombre: entrada mediante teclado (DTMF)

Personas que llaman pueden usar marcado por nombre para llegar a los usuarios mediante la especificación de ya sea el nombre completo o parcial de la persona que están intentando ponerse en contacto con. Existen diversos formatos que se pueden usar cuando se escribe el nombre.

Para realizar búsquedas en el directorio de su organización, los usuarios pueden usar la tecla 0 (cero) para indicar un espacio entre el nombre y el apellidos, o viceversa. Cuando especifica el nombre, se les pedirá a terminar su entrada de teclado con la tecla #. Por ejemplo, "Después de introducir el nombre de la persona que busca, pulse #". Si se encuentran varios nombres, se proporcionará una lista de nombres al autor de la llamada para que seleccione uno.
  
Las personas pueden realizar búsquedas por nombre en su organización empleando los siguientes formatos de búsqueda con el teclado del teléfono:
  
|Formato de nombre|Tipo de búsqueda|Ejemplo|Resultado de búsqueda|
|:-----|:-----|:-----|:-----|
|Nombre + Apellidos |Completo  |Amos0Marble# |Amos Marble |
|Apellidos + Nombre |Completo |Marble0Amos#  |Amos Marble |
|FirstName  |Completo   |Amos#   |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus |
|LastName (apellidos) |Completo |Marble#  |Pulse 1 para Amos Marble  <br/> Pulse 2 para Mary Marble |
|Nombre o Apellidos |Parcial |Mar# |Pulse 1 para Mary Marble  <br/> Pulse 2 para Mary Jones  <br/> Pulse 3 para Amos Marcus |
|Nombre + Apellidos |Parcial |Mar0Amos# |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus |
|Apellidos + Nombre |Parcial |Mar0Am# |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus |

En las búsquedas de personas a través del teclado del teléfono se pueden utilizar diferentes caracteres especiales. Por ejemplo, se pedirá la persona a usar la tecla almohadilla (#), mientras que cero (0) se utiliza para un espacio entre los nombres. Al pulsar la tecla de asterisco (*) se repetirá la lista de nombres coincidentes.
  
|Carácter especial del teclado del teléfono|Significado|
|:-----|:-----|
|#   |Carácter de fin al introducir un nombre. |
|0   |Espacio entre nombres. |
|*    |Repetir la lista de nombres coincidentes. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Marcado por nombre: reconocimiento de nombres por voz

Pueden buscar personas para que otros usuarios de su organización mediante su voz (reconocimiento de voz). Puede también llegan cualquier persona de Active Directory la compañía diciendo el nombre de la persona que intenta buscar. Uso de las entradas de voz puede reconocer nombres en diversos formatos, incluidos FirstName, LastName, FirstName + LastName (apellidos), o LastName (apellidos) + FirstName.
  
Cuando se habilita el reconocimiento de voz para un operador automático, entrada de teclado de teléfono (DTMF) no se deshabilitará, por lo que se pueden usar ambos tipos de entrada. Entrada de teclado de teléfono no se puede deshabilitar y puede usarse en cualquier momento, incluso si está habilitado el reconocimiento de voz en el operador automático.
  
Al igual que sucede con la entrada mediante el teclado del teléfono, si se encuentran varios nombres, se proporcionará una lista de nombres al autor de la llamada para que seleccione uno.
  
Los autores de llamadas pueden decir los nombres en los siguientes formatos:
  
|Nombre con voz|Tipo de búsqueda|Ejemplo|Resultado de búsqueda|
|:-----|:-----|:-----|:-----|
|Nombre + Apellidos |Completo |Amos Marble |Amos Marble |
|Apellidos + Nombre |Completo  |Marble Amos |Amos Marble |
|FirstName |Completo |Amos |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Amos Jones |
|LastName (apellidos) |Completo |Marble |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Ben Marble |

> [!NOTE]
> Puede tardar hasta 36 horas para un nuevo usuario para que su nombre aparezca en el directorio de marcado por nombre con el reconocimiento de voz debido a los retrasos de la replicación de Active Directory.
  
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

Usar el operador de un operador automático es una configuración opcional que proporciona el autor de la llamada con una opción para hablar con un operador humano.
  
Tecla 0 y el comando de voz "Operador" dirigen la llamada al operador designado de forma predeterminada. Este es el caso de todos los idiomas admitidos para el reconocimiento de voz. También puede usar **Las opciones de menú** para establecer un valor personalizado para el operador.
  
El operador se puede establecer en:
  
- Un usuario de Microsoft Teams o un Skype para la empresa en usuario local que esté habilitado para Enterprise Voice.
  
- Otro operador automático configurado para su organización.
- Cualquier cola de llamadas que tenga su organización. Para ver más información acerca de las colas de llamadas, vea [crear una cola de llamada en la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

### <a name="business-hours-and-call-handling"></a>Horario laboral y administración de llamadas

Horario se establecen en cada operador automático. Si no se establece el horario laboral, todos los días y todas las horas en el día se consideran horario debido a que una programación de 24 horas 7 se establece de forma predeterminada. Horario se puede establecer con saltos en el tiempo durante el día y todas las horas que no se han establecido como horario se consideran fuera del horario laboral. Puede establecer diferentes opciones de control de llamadas entrantes y saludos diferentes (que son opcionales), y ambos se pueden establecer para el horario laboral y fuera del horario laboral.
  
Cada operador automático tiene opciones de control de llamada que se pueden establecer:
  
- Puede hacer que la llamada se desconecte después del mensaje de saludo.
- También puede:
  - Redirigir la llamada a un usuario de Microsoft Teams que tiene una licencia de **Sistema telefónico** que esté habilitado para Enterprise Voice o planes de llamada ha asignado a ellos. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione una **persona de su empresa** y establezca que las llamadas de esta persona se desvíen de manera automática directamente al correo de voz.

  
  - Redirigir la llamada a una cola de llamada. Para ver más información acerca de las colas de llamadas, vea [crear una cola de llamada en la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

  - Redirigir la llamada a otro operador automático que haya configurado.
- Crear opciones de menú y reproducir un mensaje con instrucciones para el autor de la llamada. Por ejemplo: "Pulse 1 para Ventas, pulse 2 para Servicios. Para hablar con el operador, pulse 0 en cualquier momento".

### <a name="menu-options"></a>Opciones de menú

Operadores automáticos de nube permiten crear mensajes de menú ("Presione 1 para ventas, presione 2 para servicios de") y configure las opciones de menú para enrutar las llamadas en función de lo que el usuario selecciona. La configuración de opciones de menú para un operador automático permite a una organización proporcionar instrucciones interactivas para que las personas lleguen a su destino con mayor rapidez, sin necesidad de que un operador humano administre las llamadas entrantes. Indicadores de menú se pueden crear mediante texto a voz (mensajes generados por el sistema) o cargar un archivo de audio que se ha registrado. El reconocimiento de voz usa comandos de voz para facilitar la navegación sin entrada manual, pero los autores de llamadas pueden usar también el teclado de su teléfono para navegar por los menús.
  
Las teclas de 0 a 9 se pueden asignar a **Las opciones de menú** en un operador automático mediante el Skype para el centro de administración de negocio. Pueden crear conjuntos de opciones de menú diferentes para el horario laboral y el no laboral, y puede activar o desactivar Marcado por nombre en las **opciones del menú**. Se pueden asignar las teclas para transferir las llamadas a:
  
- Un operador, que tiene asignada la tecla 0 de forma predeterminada. Sin embargo, se puede volver a asignarse a cualquier otra tecla, o quitado del menú.
- Una cola de llamada.
- Otro operador automático. Menús de varios niveles se pueden configurar seleccionando una **Opción de menú** en el operador automático de uno a otro operador automático con su propio conjunto de opciones de menú, que se llama a un operador automático "anidadas".
- Un usuario de Microsoft Teams que tenga un **Sistema telefónico** de licencia que esté habilitado para Enterprise Voice o planes de llamada ha asignado a ellos. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione una **persona de su empresa** y establezca que las llamadas de esta persona se desvíen de manera automática directamente al correo de voz.
  
El nombre de cada opción de menú se convierte en una palabra clave de reconocimiento de voz si se ha habilitado el reconocimiento de voz. Por ejemplo, los autores de llamadas pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1, o simplemente puede dicen "Sales" para seleccionar la misma opción de menú denominada "Sales".
  
Para configurar un operador automático y las opciones de menú, vaya a [configurar un operador automático de la nube](create-a-phone-system-auto-attendant.md).
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Asignación de números de teléfono para un operador automático

Puede asignar un Microsoft llamar al número de plan de servicio o un número de híbrido de enrutamiento directa a su operador automático. Para obtener información detallada, vea [Planear el enrutamiento directo](direct-routing-plan.md) .

Para asignar un número de servicio, deberá obtener o transferir su pago existente o un servicio gratuito números. Una vez que obtenga el teléfono de pago o números de teléfono gratuito de servicio, se mostrarán en el <!-- validate nav path --> **Skype para el centro de administración de negocio** > **voz** > **los números de teléfono**y la ya se encuentra el **tipo de número de** aparecer como **servicio - gratuito**. Para obtener sus números de servicio, vea [los números de teléfono del servicio de introducción de Skype para profesionales y los equipos de Microsoft](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) o bien, si desea transferir y el número de servicio existente, vea [transferir los números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener números de servicio. Vaya [administrar números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo.
  
## <a name="related-topics"></a>Temas relacionados

[Esto es lo obtiene con el Sistema telefónico de Office 365](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Ejemplo de pequeña empresa: configurar un operador automático](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)
