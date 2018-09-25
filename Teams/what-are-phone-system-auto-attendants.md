---
title: ¿Qué son los operadores automáticos de Sistema telefónico?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
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
description: 'Obtenga información sobre qué son automáticos de sistema telefónico (nube PBX) y cómo usarlas. '
ms.openlocfilehash: d8edb924b030c9008374c8d6f49df5328b630677
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013806"
---
# <a name="what-are-phone-system-auto-attendants"></a>¿Qué son los operadores automáticos de Sistema telefónico?

Sistema telefónico en Office 365 operadores automáticos se pueden usar para crear un sistema de menús para la organización que permite a los autores de llamadas externas e internas mover a través de un sistema de menús para localizar y colocar o transferir las llamadas a los usuarios de la compañía o los departamentos de la organización.
  
Cuando una persona realiza una llamada, se le presentan una serie de instrucciones de voz que le ayudan a llamar a un usuario directamente o a localizar a alguien de la organización y, después, llamarle. Un operador automático es una serie de mensajes de voz o un archivo de audio que escuchen los autores de llamadas en lugar de un operador humano cuando llaman a una organización. Un operador automático permite que los autores de llamadas se muevan por el sistema de menús, llamen y localicen a usuarios utilizando el teclado del teléfono (DTMF) o su propia voz gracias al reconocimiento de voz. 
  
Para configurar un operador automático para el sistema telefónico en Office 365, vaya a [configurar un operador automático de sistema telefónico](/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).
  
Un operador automático de sistema telefónico tiene las siguientes características:
  
- Puede transmitir saludos corporativos o informativos.
    
- Puede proporcionar menús corporativos personalizados. Estos menús se pueden personalizar para que tengan más de un nivel.
    
- Proporciona búsqueda en el directorio que permite a las personas que llaman al buscar en el directorio de la organización para un nombre.
    
- Permite que una persona que llama en para llegar a o dejar un mensaje para una persona de su organización.
    
## <a name="getting-started"></a>Introducción

Para comenzar a utilizar operadores automáticos, es importante recordar que:
  
- Su organización debe tener (como mínimo) una licencia Enterprise E3 plus **Sistema telefónico** o una licencia Enterprise E5. El número de licencias de usuario de **Sistema telefónico** que se les asigna la repercusión en el número del servicio de números que está disponible para usarse en operadores automáticos. El número de operadores automáticos que puede tener depende de las licencias números de **Sistema telefónico** y **Conferencias de Audio** que se asignan en la organización. Para obtener más información acerca de las licencias, vaya [Skype para profesionales y los equipos de Microsoft complemento licencias](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
    > [!TIP]
    > Para redirigir las llamadas a un operador o una opción de menú que es un usuario con una licencia de **Sistema telefónico** en línea, debe habilitarlos para Enterprise Voice o asignar planes de llamada a ellos. Vea[Asignar Skype para licencias de negocio y equipos de Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). También puede usar Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obtener y usar números de servicio gratuito para los operadores automáticos, debe configurar Communications créditos. Para hacer esto, vea [¿Cuáles son las comunicaciones créditos?](what-are-communications-credits.md) y [Configurar Communications créditos para su organización](set-up-communications-credits-for-your-organization.md).
    
    > [!IMPORTANT]
    > Los números de teléfono de usuario (suscriptor) no se pueden asignar a los operadores automáticos; solo se pueden usar números de teléfono de servicio de pago y gratuitos. 
  
## <a name="feature-overview"></a>Información general sobre las características

### <a name="dial-by-name"></a>Marcado por nombre

El Marcado por nombre es una característica de un operador automático que se conoce como búsqueda en directorios. Permite a las personas que llaman a su operador automático para usar voz (reconocimiento de voz) o su teclado de teléfono (DTMF) para escribir un nombre completo o parcial para buscar en el directorio de la compañía, localice a la persona y, a continuación, tienen transferir la llamada a ellos. Si dispone de Skype para los usuarios empresariales en línea, **no es necesarios que tenga un número de teléfono o llamar a planes les ha asignado, pero deben tener una licencia de sistema telefónico** para que sean accesibles cuando realizan búsquedas utilizando marcado por nombre. Marcado por nombre incluso podrán buscar y transferir las llamadas a Skype para los usuarios en línea de negocio que se hospedan en distintos países o regiones para las organizaciones multinacionales.
  
> [!CAUTION]
> Las implementaciones locales de los usuarios de Lync Server 2010 no aparecerá en el directorio cuando alguien busca en ellos. 
  
### <a name="maximum-directory-size"></a>Tamaño máximo de directorio

No hay ningún límite en el tamaño de Active Directory para el que se admite marcado por nombre cuando se usa el teclado de teléfono para buscar para escribir nombres parciales o completos (FirstName + LastName (apellidos) y también LastName (apellidos) + FirstName). Sin embargo, el tamaño de la lista Nombre máximo que un operador automático solo puede admite el uso de reconocimiento de nombre con voz es 80.000 usuarios.
  
||||
|:-----|:-----|:-----|
|**Tipo de entrada** <br/> |**Formato de búsqueda** <br/> |**Número máximo de usuarios en una organización** <br/> |
|DTMF (entrada con teclado)  <br/> |Parcial  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre  <br/> |Sin límite  <br/> |
|Voz (entrada de voz)  <br/> |FirstName  <br/> LastName (apellidos)  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre  <br/> |80.000 usuarios  <br/> |
   
> [!NOTE]
> Si usa marcado por nombre con voz el reconocimiento de voz, pero de Active Directory la organización es mayor que 80.000 usuarios y que no ha limitado el ámbito de marcado por nombre mediante la característica de ámbito de marcado, seguirán funcionando para los llamadores con un teclado de teléfono marcado por nombre , y las entradas de voz estará disponibles para todos los demás escenarios. Puede usar la característica de ámbito de marcado para limitar los nombres que se pueden contactar cambiado el ámbito de Marcado por nombre de un operador automático determinado. 
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Marcado por nombre: entrada mediante teclado (DTMF)

Personas que llaman pueden usar marcado por nombre para llegar a los usuarios mediante la especificación de ya sea el nombre completo o parcial de la persona que están intentando ponerse en contacto con. Lo bueno es que no hay diversos formatos que se pueden usar cuando se escribe el nombre.
  
Para realizar búsquedas en el directorio de su organización, los usuarios pueden usar la tecla 0 (cero) para indicar un espacio entre el nombre y el apellidos, o viceversa. Al introducir el nombre, se les pedirá que finalicen la entrada mediante teclado con la tecla # (almohadilla). Por ejemplo, "Después de introducir el nombre de la persona que busca, pulse #". Si se encuentran varios nombres, se proporcionará una lista de nombres al autor de la llamada para que seleccione uno.
  
Las personas pueden realizar búsquedas por nombre en su organización empleando los siguientes formatos de búsqueda con el teclado del teléfono:
  
|||||
|:-----|:-----|:-----|:-----|
|**Formato de nombre** <br/> |**Tipo de búsqueda** <br/> |**Ejemplo** <br/> |**Resultado de búsqueda** <br/> |
|Nombre + Apellidos  <br/> |Completo  <br/> |Amos0Marble#  <br/> |Amos Marble  <br/> |
|Apellidos + Nombre  <br/> |Completo  <br/> |Marble0Amos#  <br/> |Amos Marble  <br/> |
|FirstName  <br/> |Completo  <br/> |Amos#  <br/> |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus  <br/> |
|LastName (apellidos)  <br/> |Completo  <br/> |Marble#  <br/> |Pulse 1 para Amos Marble  <br/> Pulse 2 para Mary Marble  <br/> |
|Nombre o Apellidos  <br/> |Parcial  <br/> |Mar#  <br/> |Pulse 1 para Mary Marble  <br/> Pulse 2 para Mary Jones  <br/> Pulse 3 para Amos Marcus  <br/> |
|Nombre + Apellidos  <br/> |Parcial  <br/> |Mar0Amos#  <br/> |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus  <br/> |
|Apellidos + Nombre  <br/> |Parcial  <br/> |Mar0Am#  <br/> |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus  <br/> |
   
En las búsquedas de personas a través del teclado del teléfono se pueden utilizar diferentes caracteres especiales. Por ejemplo, se pedirá la persona a usar la tecla almohadilla (#), mientras que cero (0) se utiliza para un espacio entre los nombres. Al pulsar la tecla de asterisco (*) se repetirá la lista de nombres coincidentes.
  
|||
|:-----|:-----|
|**Carácter especial del teclado del teléfono** <br/> |**Significado** <br/> |
|# (almohadilla)  <br/> |Carácter de fin al introducir un nombre.  <br/> |
|0 (cero)  <br/> |Espacio entre nombres.  <br/> |
|* (asterisco)  <br/> |Repetir la lista de nombres coincidentes.  <br/> |
   
### <a name="dial-by-name---name-recognition-with-speech"></a>Marcado por nombre: reconocimiento de nombres por voz

Pueden buscar personas para que otros usuarios de su organización mediante su voz (reconocimiento de voz). Puede también llegan cualquier persona de Active Directory la compañía diciendo el nombre de la persona que intenta buscar. Uso de las entradas de voz puede reconocer nombres en diversos formatos, incluidos FirstName, LastName, FirstName + LastName (apellidos), o LastName (apellidos) + FirstName.
  
Cuando se habilita el reconocimiento de voz para un operador automático, entrada de teclado de teléfono (DTMF) no se deshabilitará, por lo que se pueden usar ambos tipos de entrada. Entrada de teclado de teléfono no se puede deshabilitar y puede usarse en cualquier momento, incluso si está habilitado el reconocimiento de voz en el operador automático.
  
Al igual que sucede con la entrada mediante el teclado del teléfono, si se encuentran varios nombres, se proporcionará una lista de nombres al autor de la llamada para que seleccione uno.
  
Los autores de llamadas pueden decir los nombres en los siguientes formatos:
  
|||||
|:-----|:-----|:-----|:-----|
|**Nombre con voz** <br/> |**Tipo de búsqueda** <br/> |**Ejemplo** <br/> |**Resultado de búsqueda** <br/> |
|Nombre + Apellidos  <br/> |Completo  <br/> |Amos Marble  <br/> |Amos Marble  <br/> |
|Apellidos + Nombre  <br/> |Completo  <br/> |Marble Amos  <br/> |Amos Marble  <br/> |
|FirstName  <br/> |Completo  <br/> |Amos  <br/> |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Amos Jones  <br/> |
|LastName (apellidos)  <br/> |Completo  <br/> |Marble  <br/> |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Ben Marble  <br/> |
   
> [!NOTE]
> Puede tardar hasta 36 horas para un nuevo usuario para que su nombre aparezca en el directorio de marcado por nombre con el reconocimiento de voz. 
  
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
> Puede establecer el botón que se envían para el **operador** a una clave diferente mediante el uso de **Las opciones de menú**. 
  
Puede elegir entre las siguientes opciones para designar un operador:
  
- Un Skype para el usuario en línea de negocio que tiene un **Sistema telefónico** de licencia que esté habilitado para Enterprise Voice o planes de llamada ha asignado a ellos. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione una **persona de su empresa** y establezca que las llamadas de esta persona se desvíen de manera automática directamente al correo de voz.
    
    > [!NOTE]
    > Los usuarios alojados en implementaciones locales con Lync Server 2010 no se puede utilizar como un operador. 
  
- Otro operador automático configurado para su organización.
    
- Cualquier cola de llamadas que tenga su organización. Para ver más información acerca de las colas de llamadas, vea [crear una cola de llamadas de sistema telefónico](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).
    
### <a name="business-hours-and-call-handling"></a>Horario laboral y administración de llamadas

Horario se establecen en cada operador automático. Si no se establece el horario laboral, todos los días y todas las horas en el día se consideran horario debido a que una programación de 24 horas 7 se establece de forma predeterminada. Horario se puede establecer con saltos en el tiempo durante el día y todas las horas que no se han establecido como horario se consideran fuera del horario laboral. Puede establecer diferentes opciones de control de llamadas entrantes y saludos diferentes (que son opcionales), y ambos se pueden establecer para el horario laboral y fuera del horario laboral.
  
Cada operador automático tiene opciones de control de llamada que se pueden establecer:
  
- Puede hacer que la llamada se desconecte después del mensaje de saludo.
    
- También puede:
    
  - Redirigir la llamada a un Skype para el usuario en línea de negocio que tiene una licencia de **Sistema telefónico** que esté habilitado para Enterprise Voice o planes de llamada ha asignado a ellos. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione una **persona de su empresa** y establezca que las llamadas de esta persona se desvíen de manera automática directamente al correo de voz.
    
    > [!NOTE]
    > Los usuarios alojados en implementaciones locales no se admite el uso de Lync Server 2010. 
  
  - Redirigir la llamada a una cola de llamada. Para ver más información acerca de las colas de llamadas, vea [crear una cola de llamadas de sistema telefónico](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).
    
  - Redirigir la llamada a otro operador automático que haya configurado.
    
- Crear opciones de menú y reproducir un mensaje con instrucciones para el autor de la llamada. Por ejemplo: "Pulse 1 para Ventas, pulse 2 para Servicios. Para hablar con el operador, pulse 0 en cualquier momento".
    
### <a name="menu-options"></a>Opciones de menú

Operadores automáticos de teléfono del sistema le permiten crear mensajes de menú ("Presione 1 para ventas, presione 2 para servicios de") y configure las opciones de menú para enrutar las llamadas en función de lo que el usuario selecciona. La configuración de opciones de menú para un operador automático permite a una organización proporcionar instrucciones interactivas para que las personas lleguen a su destino con mayor rapidez, sin necesidad de que un operador humano administre las llamadas entrantes. Indicadores de menú se pueden crear mediante texto a voz (mensajes generados por el sistema) o cargar un archivo de audio que se ha registrado. El reconocimiento de voz usa comandos de voz para facilitar la navegación sin entrada manual, pero los autores de llamadas pueden usar también el teclado de su teléfono para navegar por los menús.
  
Las teclas de 0 a 9 se pueden asignar a **Las opciones de menú** en un operador automático mediante el Skype para el centro de administración de negocio. Pueden crear conjuntos de opciones de menú diferentes para el horario laboral y el no laboral, y puede activar o desactivar Marcado por nombre en las **opciones del menú**. Se pueden asignar las teclas para transferir las llamadas a:
  
- Un operador, que tiene asignada la tecla 0 de forma predeterminada. Sin embargo, se puede volver a asignarse a cualquier otra tecla, o quitado del menú.
    
- Una cola de llamada.
    
- Otro operador automático. Menús de varios niveles se pueden configurar seleccionando una **Opción de menú** en el operador automático de uno a otro operador automático con su propio conjunto de opciones de menú, que se llama a un operador automático "anidadas".
    
- Un Skype para el usuario en línea de negocio que tiene un **Sistema telefónico** de licencia que esté habilitado para Enterprise Voice o planes de llamada ha asignado a ellos. Puede configurarlo para que se pueda enviar un correo de voz a la persona que llama. Para ello, seleccione una **persona de su empresa** y establezca que las llamadas de esta persona se desvíen de manera automática directamente al correo de voz.
    
    > [!NOTE]
    > Los usuarios alojados en implementaciones locales con Lync Server 2010 no se puede usar en **Las opciones de menú**. 
  
El nombre de cada opción de menú se convierte en una palabra clave de reconocimiento de voz si se ha habilitado el reconocimiento de voz. Por ejemplo, los autores de llamadas pueden decir "Uno" para seleccionar la opción de menú asignada a la tecla 1, o simplemente puede dicen "Sales" para seleccionar la misma opción de menú denominada "Sales".
  
Para configurar un operador automático y las opciones de menú, vaya a [configurar un operador automático de sistema telefónico](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).
  
### <a name="getting-service-numbers-for-an-auto-attendant"></a>Obtener números de servicio para un operador automático

Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. Una vez que obtenga el teléfono de pago o números de teléfono gratuito de servicio, se mostrarán en la **Skype para el centro de administración de negocio** > **voz** > **los números de teléfono**y la ya se encuentra el **tipo de número de** aparecer como **servicio - gratuito **. Para obtener sus números de servicio, vea [los números de teléfono del servicio de introducción de Skype para profesionales y los equipos de Microsoft](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) o bien, si desea transferir y el número de servicio existente, vea [transferir los números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si está fuera de los Estados Unidos, no puede usar el Skype para el centro de administración de negocio para obtener números de servicio. Vaya [administrar números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo.
  
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Cambiar la identificación de llamada del usuario para que sea el número de teléfono de la cola de llamadas

Puede proteger la identidad de un usuario cambiando su identificador de llamada para las llamadas salientes a una cola de llamadas en lugar de crear una directiva con el cmdlet **New-CallingLineIdentity**.
  
Para ello, ejecute:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

A continuación, aplique la directiva al usuario mediante el cmdlet **Grant-CallingLineIdentity**. Para ello, ejecute:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Puede obtener más información acerca de cómo realizar cambios en la configuración de identificador de autor de la llamada de la organización [cómo se puede usar el identificador de autor de la llamada de la organización](/SkypeForBusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).
  
## <a name="related-topics"></a>Temas relacionados
[Esto es lo que conseguirá con Sistema telefónico en Office 365](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 