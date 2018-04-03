---
title: ¿Cuáles son los operadores de sistema de teléfono automáticos?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 01/22/2018
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Obtenga información acerca de qué son los operadores automáticos de sistema telefónico (PBX nube) y cómo utilizarlos. '
ms.openlocfilehash: a1253419bdd321efd99a4ea375655d52f154b6ab
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="what-are-phone-system-auto-attendants"></a>¿Cuáles son los operadores de sistema de teléfono automáticos?

Sistema de teléfono en Office 365 operadores automáticos pueden utilizarse para crear un sistema de menús para su organización que permite a los llamadores externos e internos se mueven a través de un sistema de menús para localizar y colocar o transferir llamadas a los usuarios de la empresa o departamentos de la organización.
  
Cuando una persona realiza una llamada, se le presentan una serie de instrucciones de voz que le ayudan a llamar a un usuario directamente o a localizar a alguien de la organización y, después, llamarle. Un operador automático es una serie de mensajes de voz o un archivo de sonido que oirán en lugar de un operador humano cuando llaman a una organización. Un operador automático permite que los autores de llamadas se muevan por el sistema de menús, llamen y localicen a usuarios utilizando el teclado del teléfono (DTMF) o su propia voz gracias al reconocimiento de voz. 
  
Para configurar un operador automático para el sistema de teléfono en Office 365, vaya a [configurar un operador automático de sistema de teléfono](set-up-a-phone-system-auto-attendant.md).
  
Un operador automático de sistema telefónico tiene las siguientes características:
  
- Puede transmitir saludos corporativos o informativos.
    
- Puede proporcionar menús corporativos personalizados. Estos menús se pueden personalizar para que tengan más de un nivel.
    
- Ofrece búsqueda de directorio que permite a las personas que llaman al buscar un nombre en el directorio de la organización.
    
- Permite que quien llama a alcanzar o dejar un mensaje para una persona en su organización.
    
## <a name="getting-started"></a>Introducción

Para comenzar a utilizar operadores automáticos, es importante recordar que:
  
- La organización debe tener (como mínimo) una licencia Enterprise E3 plus **Sistema de teléfono** o una licencia de Enterprise E5. El número de licencias de usuario de **Sistema telefónico** se asignan impactos numera el número de servicio que está disponible para utilizarse para operadores automáticos. El número de operadores automáticos que puede tener depende de las licencias de **Conferencias de Audio** y **Sistema de teléfono** número asignados en su organización. Para obtener más información acerca de licencias, vaya [Skype para negocios y equipos de Microsoft licencias adicionales](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Para redirigir las llamadas a un operador o una opción de menú es un usuario con una licencia de **Sistema de teléfono** en línea, debe habilitarlos para Telefonía IP empresarial o llamar a planes les asigne. Consulte[Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). También puede usar Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obtener y utilizar números de servicio gratuito para los operadores automáticos, es necesario configurar comunicaciones créditos. Para ello, consulte [¿qué comunicaciones créditos?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) y [Configurar comunicaciones créditos para su organización](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
    > [!IMPORTANT]
    > Los números de teléfono de usuario (suscriptor) no se pueden asignar a los operadores automáticos; solo se pueden usar números de teléfono de servicio de pago y gratuitos. 
  
## <a name="feature-overview"></a>Información general sobre las características

### <a name="dial-by-name"></a>Marcado por nombre

El Marcado por nombre es una característica de un operador automático que se conoce como búsqueda en directorios. Permite a las personas que llaman a su operador automático utilizar voz (reconocimiento de voz) o el teclado del teléfono (DTMF) para introducir un nombre completo o parcial para buscar en el directorio de la empresa, localizar a la persona y que, a continuación, transferir la llamada a ellos. Si tienes Skype para usuarios de negocios en línea, **no están obligados a tener un número de teléfono o llamar a planes les ha asignado, pero deben tener una licencia de sistema telefónico** para que sean accesibles cuando realizan búsquedas utilizando marcado por su nombre. Marcado por nombre incluso podrá buscar y transferir llamadas a Skype para usuarios de negocios en línea que están alojados en diferentes países o regiones para organizaciones multinacionales.
  
> [!CAUTION]
> Las implementaciones locales de los usuarios de Lync Server 2010 no aparecerá en el directorio cuando alguien busca en ellos. 
  
### <a name="maximum-directory-size"></a>Tamaño máximo de directorio

No hay ningún límite en el tamaño de Active Directory que se admite marcado por su nombre al utilizar el teclado del teléfono para buscar para introducir nombres parciales o completos (FirstName LastName y también apellidos + FirstName). Sin embargo, el tamaño de la lista de nombre máximo que un operador automático solo puede admitir utilizando reconocimiento de nombre con voz es 80.000 usuarios.
  
||||
|:-----|:-----|:-----|
|**Tipo de entrada** <br/> |**Formato de búsqueda** <br/> |**Número máximo de usuarios en una organización** <br/> |
|DTMF (entrada con teclado)  <br/> |Parcial  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre  <br/> |Sin límite  <br/> |
|Voz (entrada de voz)  <br/> |FirstName  <br/> Apellidos  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre  <br/> |usuarios de 80.000  <br/> |
   
> [!NOTE]
> Si utiliza marcado por su nombre con voz el reconocimiento, pero Active Directory su organización es más grande que 80.000 usuarios y que no ha limitado el ámbito de marcado por nombre mediante la característica de marcado ámbito, seguirá funcionando para los llamadores utilizando un teclado de teléfono marcado por nombre , y las entradas de voz estará disponibles para todos los demás casos. Puede usar la característica de ámbito de marcado para limitar los nombres que se pueden contactar cambiado el ámbito de Marcado por nombre de un operador automático determinado. 
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Marcado por nombre: entrada mediante teclado (DTMF)

Personas que llaman pueden usar marcado por nombre para llegar a los usuarios al especificar tanto el nombre completo o parcial de la persona que están intentando llegar a. Lo bueno es que hay varios formatos que se pueden utilizar cuando se escribe el nombre.
  
Para realizar búsquedas en el directorio de su organización, los usuarios pueden usar la tecla 0 (cero) para indicar un espacio entre el nombre y el apellidos, o viceversa. Al introducir el nombre, se les pedirá que finalicen la entrada mediante teclado con la tecla # (almohadilla). Por ejemplo, "Después de introducir el nombre de la persona que busca, pulse #". Si se encuentran varios nombres, se proporcionará una lista de nombres al autor de la llamada para que seleccione uno.
  
Las personas pueden realizar búsquedas por nombre en su organización empleando los siguientes formatos de búsqueda con el teclado del teléfono:
  
|||||
|:-----|:-----|:-----|:-----|
|**Formato de nombre** <br/> |**Tipo de búsqueda** <br/> |**Ejemplo** <br/> |**Resultado de búsqueda** <br/> |
|Nombre + Apellidos  <br/> |Completo  <br/> |Amos0Marble#  <br/> |Amos Marble  <br/> |
|Apellidos + Nombre  <br/> |Completo  <br/> |Marble0Amos#  <br/> |Amos Marble  <br/> |
|FirstName  <br/> |Completo  <br/> |Amos#  <br/> |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus  <br/> |
|Apellidos  <br/> |Completo  <br/> |Marble#  <br/> |Pulse 1 para Amos Marble  <br/> Pulse 2 para Mary Marble  <br/> |
|Nombre o Apellidos  <br/> |Parcial  <br/> |Mar#  <br/> |Pulse 1 para Mary Marble  <br/> Pulse 2 para Mary Jones  <br/> Pulse 3 para Amos Marcus  <br/> |
|Nombre + Apellidos  <br/> |Parcial  <br/> |Mar0Amos#  <br/> |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus  <br/> |
|Apellidos + Nombre  <br/> |Parcial  <br/> |Mar0Am#  <br/> |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus  <br/> |
   
En las búsquedas de personas a través del teclado del teléfono se pueden utilizar diferentes caracteres especiales. Por ejemplo, se pedirá la persona para utilizar la tecla almohadilla (#), mientras que cero (0) se utiliza para un espacio entre nombres. Al pulsar la tecla de asterisco (*) se repetirá la lista de nombres coincidentes.
  
|||
|:-----|:-----|
|**Carácter especial del teclado del teléfono** <br/> |**Significado** <br/> |
|# (almohadilla)  <br/> |Carácter de fin al introducir un nombre.  <br/> |
|0 (cero)  <br/> |Espacio entre nombres.  <br/> |
|* (asterisco)  <br/> |Repetir la lista de nombres coincidentes.  <br/> |
   
### <a name="dial-by-name---name-recognition-with-speech"></a>Marcado por nombre: reconocimiento de nombres por voz

La gente puede buscar otros usuarios en su organización con su voz (reconocimiento de voz). También pueden alcanzar cualquiera de Active Directory de la empresa diciendo el nombre de la persona que intenta buscar. Utilizando las entradas de voz pueda reconocer nombres en diversos formatos, incluidos FirstName, LastName, FirstName + apellidos, o apellidos + FirstName.
  
Cuando se habilita el reconocimiento de voz para un operador automático, entrada de teclado del teléfono (DTMF) no deshabilitado, por lo que pueden utilizar ambos tipos de entrada. Entrada de teclado de teléfono no se puede deshabilitar y puede utilizarse en cualquier momento, incluso si el reconocimiento de voz está habilitado en el operador automático.
  
Al igual que sucede con la entrada mediante el teclado del teléfono, si se encuentran varios nombres, se proporcionará una lista de nombres al autor de la llamada para que seleccione uno.
  
Los autores de llamadas pueden decir los nombres en los siguientes formatos:
  
|||||
|:-----|:-----|:-----|:-----|
|**Nombre con voz** <br/> |**Tipo de búsqueda** <br/> |**Ejemplo** <br/> |**Resultado de búsqueda** <br/> |
|Nombre + Apellidos  <br/> |Completo  <br/> |Amos Marble  <br/> |Amos Marble  <br/> |
|Apellidos + Nombre  <br/> |Completo  <br/> |Marble Amos  <br/> |Amos Marble  <br/> |
|FirstName  <br/> |Completo  <br/> |Amos  <br/> |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Amos Jones  <br/> |
|Apellidos  <br/> |Completo  <br/> |Marble  <br/> |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Ben Marble  <br/> |
   
> [!NOTE]
> Puede tardar hasta 36 horas para un nuevo usuario para que su nombre aparezca en el directorio de marcado por nombre con reconocimiento de voz. 
  
### <a name="language-support"></a>Compatibilidad con idiomas

La característica de texto a voz está disponible en los siguientes idiomas:
  
||||
|:-----|:-----|:-----|
|Árabe (EG)  <br/> |Inglés (NZ)  <br/> |Coreano (KO)  <br/> |
|Chino (HK)  <br/> |Inglés (Reino Unido)  <br/> |Noruego (NO)  <br/> |
|Chino (TW)  <br/> |Inglés (Estados Unidos)  <br/> |Polaco (PL)  <br/> |
|Chino (ZH)  <br/> |Finés (FI)  <br/> |Portugués (BR)  <br/> |
|Danés (DA)  <br/> |Francés (CA)  <br/> |Portugués (PT)  <br/> |
|Neerlandés (NL)  <br/> |Francés (FR)  <br/> |Ruso (RU)  <br/> |
|Inglés (AU)  <br/> |Alemán (DE)  <br/> |Español (ES)  <br/> |
|Inglés (CA)  <br/> |Italiano (IT)  <br/> |Español (MX)  <br/> |
|Inglés (IN)  <br/> |Japonés (JP)  <br/> |Sueco (SV)  <br/> |
   
El reconocimiento de voz para operadores automáticos está disponible en los siguientes idiomas:
  
|||
|:-----|:-----|
|Chino (ZH)  <br/> |Francés (FR)  <br/> |
|Inglés (AU)  <br/> |Alemán (DE)  <br/> |
|Inglés (CA)  <br/> |Italiano (IT)  <br/> |
|Inglés (IN)  <br/> |Japonés (JP)  <br/> |
|Inglés (Reino Unido)  <br/> |Portugués (BR)  <br/> |
|Inglés (Estados Unidos)  <br/> |Español (ES)  <br/> |
|Francés (CA)  <br/> |Español (MX)  <br/> |
   
Los siguientes comandos de voz están disponibles en los catorce (14) idiomas admitidos para el reconocimiento de voz:
  
|||
|:-----|:-----|
|**Comando de voz** <br/> |**Significado** <br/> |
|Sí  <br/> |Sí (equivale a pulsar 1 para Sí).  <br/> |
|No  <br/> |No (equivale a pulsar 2 para No).  <br/> |
|Repetir  <br/> |Repite la lista de opciones (equivale a pulsar * para repetir la lista de opciones).  <br/> |
|Operador  <br/> |Salida al operador (equivale a pulsar 0 para "Operador").  <br/> |
|Menú principal  <br/> |Lleva al autor de la llamada al menú principal del operador automático.  <br/> |
|Cero  <br/> |Equivale a pulsar 0 (de forma predeterminada, igual que "Operador").  <br/> |
|Uno  <br/> |Equivale a pulsar 1.  <br/> |
|Dos  <br/> |Equivale a pulsar 2.  <br/> |
|Tres  <br/> |Equivale a pulsar 3.  <br/> |
|Cuatro  <br/> |Equivale a pulsar 4.  <br/> |
|Cinco  <br/> |Equivale a pulsar 5.  <br/> |
|Seis  <br/> |Equivale a pulsar 6.  <br/> |
|Siete  <br/> |Equivale a pulsar 7.  <br/> |
|Ocho  <br/> |Equivale a pulsar 8.  <br/> |
|Nueve  <br/> |Equivale a pulsar 9.  <br/> |
   
### <a name="using-the-operator-option"></a>Usar la opción de operador

Usar un operador en relación con un operador automático es una configuración opcional que ofrece la posibilidad a los autores de llamadas de hablar con una persona real.
  
De forma predeterminada, la tecla 0 y el comando de voz "Operador" (en todos los idiomas admitidos para el reconocimiento de voz) están asignados al operador.
  
> [!NOTE]
> Puede establecer el botón que se inserta mediante **Opciones de menú**para el **operador** a una clave distinta. 
  
Puede elegir entre las siguientes opciones para designar un operador:
  
- Un Skype para usuarios de negocios en línea que tenga un **Sistema telefónico** de licencia que está habilitado para Telefonía IP empresarial o llamar a planes tiene asignados. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione una **persona de su empresa** y establezca que las llamadas de esta persona se desvíen de manera automática directamente al correo de voz.
    
    > [!NOTE]
    > Los usuarios alojados en instalaciones con Lync Server 2010 no se puede utilizar como un operador. 
  
- Otro operador automático configurado para su organización.
    
- Cualquier cola de llamadas que tenga su organización. Para ver más información acerca de las colas de llamada, vea [crear una cola de llamada del sistema telefónico](create-a-phone-system-call-queue.md).
    
### <a name="business-hours-and-call-handling"></a>Horario laboral y administración de llamadas

Horario de oficina se establecen en cada operador automático. Si no se establece el horario laboral, todos los días y todas las horas del día se consideran horario laboral debido a una programación de 24/7 se establece de forma predeterminada. Horario de oficina puede establecerse con saltos en el tiempo durante el día y todas las horas que no están establecidas como horario se consideran fuera del horario laboral. Puede establecer diferentes opciones de manejo de llamadas entrantes y saludos diferentes (que son opcionales), y ambas pueden establecerse para el horario laboral y fuera del horario laboral.
  
Cada operador automático tiene opciones de manejo de llamadas que se pueden establecer:
  
- Puede hacer que la llamada se desconecte después del mensaje de saludo.
    
- También puede:
    
  - Redirigir la llamada a un Skype para el usuario de negocios en línea que tiene una licencia de **Sistema de teléfono** habilitado para Telefonía IP empresarial o llamar a planes tiene asignados. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione una **persona de su empresa** y establezca que las llamadas de esta persona se desvíen de manera automática directamente al correo de voz.
    
    > [!NOTE]
    > Los usuarios alojados en locales no se admite el uso de Lync Server 2010. 
  
  - Redireccionar la llamada a una cola de llamada. Para ver más información acerca de las colas de llamada, vea [crear una cola de llamada del sistema telefónico](create-a-phone-system-call-queue.md).
    
  - Redireccionar la llamada a otro operador automático que ha configurado.
    
- Crear opciones de menú y reproducir un mensaje con instrucciones para el autor de la llamada. Por ejemplo: "Pulse 1 para Ventas, pulse 2 para Servicios. Para hablar con el operador, pulse 0 en cualquier momento".
    
### <a name="menu-options"></a>Opciones de menú

Operadores automáticos de sistema de teléfono le permiten crear indicadores de menú ("Presione 1 para ventas, presione 2 para servicios") y configurar las opciones de menú para enrutar llamadas basadas en lo que el usuario selecciona. La configuración de opciones de menú para un operador automático permite a una organización proporcionar instrucciones interactivas para que las personas lleguen a su destino con mayor rapidez, sin necesidad de que un operador humano administre las llamadas entrantes. Instrucciones del menú pueden crearse mediante texto a voz (mensajes generados por el sistema) o cargar un archivo de audio que se ha registrado. El reconocimiento de voz usa comandos de voz para facilitar la navegación sin entrada manual, pero los autores de llamadas pueden usar también el teclado de su teléfono para navegar por los menús.
  
Teclas del 0 al 9 pueden asignarse a las **Opciones de menú** de un operador automático mediante el Skype para el centro de administración de negocios. Pueden crear conjuntos de opciones de menú diferentes para el horario laboral y el no laboral, y puede activar o desactivar Marcado por nombre en las **opciones del menú**. Se pueden asignar las teclas para transferir las llamadas a:
  
- Un operador, que tiene asignada la tecla 0 de forma predeterminada. Sin embargo, se puede volver a asignarse a cualquier otra tecla, o quitado del menú.
    
- Una llamada de cola.
    
- Otro operador automático. Menús de varios niveles pueden configurarse señalando una **Opción de menú** en el operador automático de uno a otro operador automático con su propio conjunto de opciones de menú, que se denomina a un operador automático "anidadas".
    
- Un Skype para usuarios de negocios en línea que tenga un **Sistema telefónico** de licencia que está habilitado para Telefonía IP empresarial o llamar a planes tiene asignados. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione una **persona de su empresa** y establezca que las llamadas de esta persona se desvíen de manera automática directamente al correo de voz.
    
    > [!NOTE]
    > Los usuarios alojados en instalaciones con Lync Server 2010 no se puede utilizar en las **Opciones de menú**. 
  
El nombre de cada opción de menú se convierte en una palabra clave de reconocimiento de voz si se ha habilitado el reconocimiento de voz. Por ejemplo, los llamadores pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1 o pueden decir simplemente "Ventas" para seleccionar la misma opción de menú denominada "Sales".
  
Para configurar un operador automático y las opciones de menú, vaya a [configurar un operador automático de sistema de teléfono](set-up-a-phone-system-auto-attendant.md).
  
### <a name="getting-service-numbers-for-an-auto-attendant"></a>Obtener números de servicio para un operador automático

Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. Una vez que obtenga el número o números de teléfono de servicio gratuito, se mostrará en el **Skype para el centro de administración de negocios** > **voz** > **números de teléfono**y la voluntad de **tipo número** en la lista aparecen como **servicio - gratis **. Para obtener los números de servicio, vea [números de teléfono de servicio de obtención de Skype para empresas y equipos de Microsoft](getting-service-phone-numbers.md) , o bien, si desea transferir y el número de servicio existente, consulte [transferir números de teléfono para Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si está fuera de los Estados Unidos, no puede utilizar el Skype para el centro de administración de negocios para obtener números de servicio. Vaya [administrar números de teléfono de la organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo.
  
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Cambiar el identificador del usuario llamador para que sea el número de teléfono de una llamada de cola

Puede proteger la identidad de un usuario cambiando su ID de llamada para las llamadas salientes a una cola de llamada en su lugar mediante la creación de una directiva con el cmdlet **New-CallingLineIdentity** .
  
Para ello, ejecute:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

A continuación, aplicar la directiva al usuario mediante el cmdlet de **Concesión CallingLineIdentity** . Para ello, ejecute:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Puede obtener más información acerca de cómo realizar cambios en la configuración del ID de llamador en su organización [identificador de uso en su organización](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="related-topics"></a>See also
[Esto es lo que conseguirá con Sistema telefónico en Office 365](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 