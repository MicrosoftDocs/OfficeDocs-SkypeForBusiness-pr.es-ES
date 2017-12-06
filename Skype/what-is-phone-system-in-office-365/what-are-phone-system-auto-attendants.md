---
title: "¿Cuáles son los operadores automáticos de sistema telefónico?"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
description: "Learn what Phone System (Cloud PBX) auto attendents are and how to use them. "
---

# ¿Cuáles son los operadores automáticos de sistema telefónico?

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](ab9f05a2-22cb-4692-a585-27f82d1b37c7.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/ab9f05a2-22cb-4692-a585-27f82d1b37c7). 
  
Mover el sistema telefónico en Office 365 los operadores automáticos de pueden usarse para crear un sistema de menús para su organización que le permite externas e internas de las personas que llaman a través de un sistema de menús para localizar y coloque o transferir llamadas a los usuarios de la compañía o los departamentos de su organización.
  
Cuando llama personas, se presentan con una serie de mensajes de voz que les ayudan a realizar una llamada a un usuario o buscar a alguien de su organización y, a continuación, realizar una llamada a ese usuario. Un operador automático es una serie de mensajes de voz o un archivo de audio que las personas que llaman escuchar en lugar de un operador cuando llaman a una organización. Un operador automático permite a las personas que llaman desplazarse por el sistema de menús, realizar llamadas, o buscar usuarios con un teclado del teléfono (DTMF) o usando el reconocimiento de voz de entradas de voz.
  
Para configurar un operador automático para el sistema telefónico en Office 365, vaya [Configurar un operador automático de sistema telefónico](set-up-a-phone-system-auto-attendant.md).
  
Un operador automático de sistema telefónico tiene las siguientes características:
  
- Puede transmitir saludos corporativos o informativos.
    
- Puede proporcionar menús corporativos personalizados. Estos menús se pueden personalizar para que tengan más de un nivel.
    
- Proporciona búsqueda en el directorio que permite a las personas que llaman para buscar un nombre en el directorio de la organización.
    
- Permite a un usuario que llama a llegar o dejar un mensaje para una persona de su organización.
    
## Introducción

Para comenzar a utilizar operadores automáticos, es importante recordar que:
  
- Licencia Enterprise E5 o una licencia Enterprise E3 plus **Sistema telefónico**, debe tener su organización (como mínimo). El número de licencias de usuario de **Sistema de teléfono** asignados desventajas el número del servicio de números que está disponible para usarse con operadores automáticos. El número de operadores automáticos que puede tener depende de las licencias de **Sistema telefónico** y **Conferencias de Audio de** número que se asignan en su organización. Para obtener más información sobre licencias, vaya[Skype para Business y Microsoft Teams licencias de complemento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Para desviar llamadas a un operador o una opción de menú que es un usuario en línea con una licencia de **Sistema telefónico**, necesitará habilitarlos para telefonía IP empresarial o asignarles llamar a los planes. Vea [Asignar Skype para Business y Microsoft Teams licencias](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). También puede usar Windows PowerShell. Ejecutar por ejemplo:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obtener y utilizar números de servicio gratuito para los operadores automáticos, debe configurar créditos de comunicaciones. Para ello, consulte [¿Qué son créditos de comunicaciones?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) y[Configurar comunicaciones créditos para su organización](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
    > [!IMPORTANT]
    > Los números de teléfono de usuario (suscriptor) no se pueden asignar a los operadores automáticos; solo se pueden usar números de teléfono de servicio de pago y gratuitos. 
  
## Información general sobre las características

### Marcado por nombre

Marcado por nombre es una característica de un operador automático que se conoce como la búsqueda en el directorio. Permite que las personas que llaman a su operador automático para usar voz (reconocimiento de voz) o el teclado del teléfono (DTMF) para escribir un nombre completo o parcial para buscar el directorio de la empresa, busque a la persona y, a continuación, tener transferir la llamada a ellos. Si dispone de Skype empresarial los usuarios, **no se necesitan tener un número de teléfono o llamar a los planes les ha asignado, pero deben tener una licencia de **Sistema telefónico**** para que sean accesibles cuando busquen con acceso telefónico por su nombre. Marcado por nombre incluso podrá encontrar y transferir llamadas a Skype empresarial los usuarios que están alojados en diferentes países o regiones para organizaciones multinacionales.
  
> [!CAUTION]
> En las implementaciones locales de los usuarios de Lync Server 2010 no tiene que aparecer en el directorio cuando alguien busca. 
  
### Tamaño máximo de directorio

No hay ningún límite en el tamaño de Active Directory para el que se admite marcado por nombre al usar el teclado del teléfono para buscar para introducir nombres completos o parciales (nombre apellidos y también Apellidos + Nombre). Sin embargo, el tamaño de la lista de nombres máximo que un operador automático solo puede admitir usando el reconocimiento de nombre con voz es 80.000 usuarios.
  
||||
|:-----|:-----|:-----|
|**Tipo de entrada** <br/> |**Formato de búsqueda** <br/> |**Número máximo de usuarios en una organización** <br/> |
|DTMF (entrada con teclado)  <br/> |Parcial  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre  <br/> |Sin límite  <br/> |
|Voz (entrada de voz)  <br/> |Nombre  <br/> Apellidos  <br/> Nombre + Apellidos  <br/> Apellidos + Nombre  <br/> |80.000 usuarios  <br/> |
   
> [!NOTE]
> Si está utilizando marcado por nombre con voz es mayor de 80.000 usuarios reconocimiento, pero Active Directory de su organización y que no ha limitado el ámbito de acceso telefónico por nombre mediante la característica de ámbito de acceso telefónico, acceso telefónico por nombre seguirán funcionando para las llamadas con un teclado numérico de teléfono , y las entradas de voz estará disponibles para todos los demás casos. Puede usar la característica de ámbito de acceso telefónico para restringir los nombres que se puede llegar al cambiar el ámbito de acceso telefónico por nombre para un operador automático determinado. 
  
### Marcado por nombre: entrada mediante teclado (DTMF)

Personas que llaman pueden usar marcado por nombre para llegar a los usuarios especificando, ya sea el nombre completo o parcial de la persona que están intentando alcanzar. La buena es que hay varios formatos que se pueden usar cuando se escribe el nombre.
  
Para realizar búsquedas en el directorio de su organización, los usuarios pueden usar la tecla 0 (cero) para indicar un espacio entre el nombre y el apellidos, o viceversa. Al introducir el nombre, se les pedirá que finalicen la entrada mediante teclado con la tecla # (almohadilla). Por ejemplo, "Después de introducir el nombre de la persona que busca, pulse #". Si se encuentran varios nombres, se proporcionará una lista de nombres al autor de la llamada para que seleccione uno.
  
Las personas pueden realizar búsquedas por nombre en su organización empleando los siguientes formatos de búsqueda con el teclado del teléfono:
  
|||||
|:-----|:-----|:-----|:-----|
|**Formato de nombre** <br/> |**Tipo de búsqueda** <br/> |**Ejemplo** <br/> |**Resultado de búsqueda** <br/> |
|Nombre + Apellidos  <br/> |Completo  <br/> |Amos0Marble#  <br/> |Amos Marble  <br/> |
|Apellidos + Nombre  <br/> |Completo  <br/> |Marble0Amos#  <br/> |Amos Marble  <br/> |
|Nombre  <br/> |Completo  <br/> |Amos#  <br/> |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus  <br/> |
|Apellidos  <br/> |Completo  <br/> |Marble#  <br/> |Pulse 1 para Amos Marble  <br/> Pulse 2 para Mary Marble  <br/> |
|Nombre o Apellidos  <br/> |Parcial  <br/> |Mar#  <br/> |Pulse 1 para Mary Marble  <br/> Pulse 2 para Mary Jones  <br/> Pulse 3 para Amos Marcus  <br/> |
|Nombre + Apellidos  <br/> |Parcial  <br/> |Mar0Amos#  <br/> |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus  <br/> |
|Apellidos + Nombre  <br/> |Parcial  <br/> |Mar0Am#  <br/> |Pulse 1 para Amos Marble  <br/> Pulse 2 para Amos Marcus  <br/> |
   
Existen varios caracteres especiales que se usan cuando busque personas mediante un teclado del teléfono. Por ejemplo, tendrá la persona que use la tecla almohadilla (#), mientras que cero (0) se utiliza para un espacio entre los nombres. Al presionar la tecla del asterisco (*) se repetirá la lista de nombres a la persona que coincidan.
  
|||
|:-----|:-----|
|**Carácter especial del teclado del teléfono** <br/> |**Significado** <br/> |
|# (almohadilla)  <br/> |Carácter de fin al introducir un nombre.  <br/> |
|0 (cero)  <br/> |Espacio entre nombres.  <br/> |
|* (asterisco)  <br/> |Repetir la lista de nombres coincidentes.  <br/> |
   
### Marcado por nombre: reconocimiento de nombres por voz

Pueden búsqueda de personas para que otras personas de su organización usando su voz (reconocimiento de voz). Puede también lleguen a cualquier usuario en Active Directory de la compañía diciendo el nombre de la persona que desee buscar. Uso de las entradas de voz puede reconocer nombres en varios formatos, incluido el nombre, apellidos, nombre apellidos, o apellidos + nombre.
  
Cuando se habilita el reconocimiento de voz para un operador automático, entrada de teclado del teléfono (DTMF) no deshabilitado, por lo que pueden utilizar ambos tipos de entrada. Entrada de teclado del teléfono no se puede deshabilitar y puede utilizarse en cualquier momento, incluso si está habilitado el reconocimiento de voz en el operador automático.
  
Al igual que sucede con la entrada mediante el teclado del teléfono, si se encuentran varios nombres, se proporcionará una lista de nombres al autor de la llamada para que seleccione uno.
  
Los autores de llamadas pueden decir los nombres en los siguientes formatos:
  
|||||
|:-----|:-----|:-----|:-----|
|**Nombre de voz** <br/> |**Tipo de búsqueda** <br/> |**Ejemplo** <br/> |**Resultado de búsqueda** <br/> |
|Nombre + Apellidos  <br/> |Completo  <br/> |Amos Marble  <br/> |Amos Marble  <br/> |
|Apellidos + Nombre  <br/> |Completo  <br/> |Marble Amos  <br/> |Amos Marble  <br/> |
|Nombre  <br/> |Completo  <br/> |Amos  <br/> |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Amos Jones  <br/> |
|Apellidos  <br/> |Completo  <br/> |Marble  <br/> |Pulse o diga 1 para Amos Marble  <br/> Pulse o diga 2 para Ben Marble  <br/> |
   
> [!NOTE]
> Puede tardar hasta 36 horas para que su nombre aparece en el directorio de acceso telefónico por nombre con el reconocimiento de voz de un usuario nuevo. 
  
### Compatibilidad con idiomas

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
   
Los siguientes comandos de voz están disponibles en los catorce (14﻿) idiomas admitidos para el reconocimiento de voz:
  
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
   
### Usar la opción de operador

Usar un operador en relación con un operador automático es una configuración opcional que ofrece la posibilidad a los autores de llamadas de hablar con una persona real.
  
De forma predeterminada, la tecla 0 y el comando de voz "Operador" (en todos los idiomas admitidos para el reconocimiento de voz) están asignados al operador.
  
> [!NOTE]
> Puede configurar el botón que se envían para el **operador** a otra clave con **Las opciones de menú**. 
  
Puede elegir entre las siguientes opciones para designar un operador:
  
- Un Skype empresarial Online usuario que tiene un **Sistema telefónico** de licencias que está habilitada para telefonía IP empresarial o llamar a los planes tiene asignados. Puede configurarlo para que la persona que llama se pueden enviar al correo de voz. Para ello, seleccione una **persona de su empresa** y establezca las llamadas automáticamente se desvíen directamente al correo de voz de la persona.
    
    > [!NOTE]
    > Los usuarios alojados en local con Lync Server 2010 no se puede utilizar como un operador. 
  
- Otro operador automático configurado para su organización.
    
- Cualquier cola llamada existente que está configurado en su organización. Para ver más información acerca de la llamada colas, vea [Crear una cola de llamada del sistema telefónico](create-a-phone-system-call-queue.md).
    
### Horario laboral y administración de llamadas

Horas de trabajo se establecen en cada operador automático. Si no las horas de trabajo, todos los días y las horas en el día se consideran horario comercial porque una programación de 24/7 se establece de forma predeterminada. Horas de trabajo se puede establecer con saltos en el tiempo durante el día y todas las horas que no están establecidas como las horas de trabajo se consideran fuera del horario laboral. Puede establecer diferentes opciones de control de llamada entrantes y saludos diferentes (que son opcionales) y puede establecerse fuera del horario laboral y las horas de trabajo.
  
Cada operador automático tiene opciones de control de llamada que se pueden establecer:
  
- Puede hacer que la llamada se desconecte después del mensaje de saludo.
    
- También puede:
    
  - Desviar la llamada a un Skype empresarial Online usuario que tiene una licencia de **Sistema telefónico** está habilitada para telefonía IP empresarial o llamar a los planes tiene asignados. Puede configurarlo para que la persona que llama se pueden enviar al correo de voz. Para ello, seleccione una **persona de su empresa** y establezca las llamadas automáticamente se desvíen directamente al correo de voz de la persona.
    
    > [!NOTE]
    > Los usuarios alojados en local con Lync Server 2010 no se admiten. 
  
  - Desviar la llamada a una cola de la llamada. Para ver más información acerca de la llamada colas, vea [Crear una cola de llamada del sistema telefónico](create-a-phone-system-call-queue.md).
    
  - Redirigir la llamada a otro operador automático que haya configurado.
    
- Crear opciones de menú y reproducir un mensaje con instrucciones para el autor de la llamada. Por ejemplo: "Pulse 1 para Ventas, pulse 2 para Servicios. Para hablar con el operador, pulse 0 en cualquier momento".
    
### Opciones de menú

Operadores automáticos de sistema de teléfono le permiten crear indicaciones de menú ("Presione 1 para ventas, presione 2 para los servicios de") y configurar las opciones de menú para dirigir las llamadas en función de lo que el usuario selecciona. Configurar las opciones de menú para un operador automático permite a una organización que proporcione una guía interactiva para obtener a la persona a su destino más rápido, sin confiar en un operador controle las llamadas entrantes. Menú indicaciones pueden crearse mediante la característica texto a voz (indicaciones generadas por el sistema) o cargar un archivo de audio que se ha registrado. Reconocimiento de voz utiliza comandos de voz para la navegación de manos libres, pero personas que llaman también pueden usar el teclado del teléfono para desplazarse por los menús.
  
Teclas de 0 a 9 se pueden asignar a **Las opciones de menú** en un operador automático con la Skype para el centro de administración de la empresa. Se pueden crear diferentes conjuntos de opciones de menú de horario comercial y después de horas, y puede habilitar o deshabilitar marcado por su nombre en el **Menú Opciones**. Para transferir las llamadas a, se pueden asignar claves:
  
- Un operador, que se asigna a la clave 0 de forma predeterminada. Sin embargo, se puede volver a asignarse a cualquier otra tecla, o quitado del menú.
    
- Una cola de la llamada.
    
- Otro operador automático. Menús de múltiples niveles se pueden configurar eligiendo una **Opción de menú** de operador automático de uno a otro operador automático con su propio conjunto de opciones de menú que se llama a un operador automático "anidadas".
    
- Un Skype empresarial Online usuario que tiene un **Sistema telefónico** de licencias que está habilitada para telefonía IP empresarial o llamar a los planes tiene asignados. Puede configurarlo para que la persona que llama se pueden enviar al correo de voz. Para ello, seleccione una **persona de su empresa** y establezca las llamadas automáticamente se desvíen directamente al correo de voz de la persona.
    
    > [!NOTE]
    > Los usuarios alojados en local con Lync Server 2010 no se pueden usar en **Las opciones de menú**. 
  
El nombre de cada opción de menú se convierte en una palabra clave de reconocimiento de voz, si se ha habilitado el reconocimiento de voz. Por ejemplo, las personas que llaman pueden decir "Uno" para seleccionar la opción de menú que se asignan a la clave 1, o simplemente puede dicen "Ventas" para seleccionar la misma opción de menú denominada "Ventas".
  
Para configurar un operador automático y las opciones de menú, vaya [Configurar un operador automático de sistema telefónico](set-up-a-phone-system-auto-attendant.md).
  
### Obtener números de servicio para un operador automático

Para poder crear y configurar los operadores automáticos, necesitará obtener o transferir su pago existente o un servicio gratuito números. Una vez creado el pago o números de teléfono gratuitos de servicio, aparecerá en la **Skype centro de administración de negocio** > **voz** > **números de teléfono** y a continuación, usará **tipo número** en la lista figurar como **servicio gratuito**. Para obtener los números de servicio, vea [Obtener números de teléfono de servicio de Skype Empresarial](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) , o bien, si desea transferir y el número de servicio existente, vea[Números de teléfono de transferencia a Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si está fuera de los Estados Unidos, no puede usar la Skype centro de administración de la empresa para obtener números de servicio. Vaya [Administrar los números de teléfono de su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo.
  
## Cambiar el identificador de usuario para que sea el número de teléfono de una cola de llamada

Puede proteger la identidad de un usuario cambiando su identificador de llamada para las llamadas salientes a una cola de llamada en su lugar mediante la creación de una directiva mediante el cmdlet **New-CallingLineIdentity**.
  
Para ello, ejecute:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

A continuación, aplicar la directiva al usuario mediante el cmdlet **Grant-CallingLineIdentity**. Para ello, ejecute:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Puede obtener más información sobre cómo realizar cambios en la configuración de identificador de llamada de su organización [Cómo se puede usar la identificación de llamadas en su organización](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## Temas relacionados

[Aquí es lo que obtiene con el sistema telefónico en Office 365](here-s-what-you-get-with-phone-system-in-office-365.md)
  
[Configurar planes de llamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

