---
title: "Configurar un operador automático de sistema de teléfono"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "Aprenda a configurar y probar los operadores automáticos de sistema telefónico (PBX nube) llamada eficaz tratamiento para su organización. "
ms.openlocfilehash: 294a91ec723d8234e2dbfec8da79441080263c30
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Configurar un operador automático de sistema de teléfono

Operadores automáticos permiten a los usuarios que llaman a su organización y navegar por un sistema de menús para obtenerlos en el departamento correcto, llame a la cola, la persona o el operador. Puede crear a un operador automático para su organización mediante el Skype para el centro de administración de negocios. Para crear un nuevo operador automático, vaya al **enrutamiento de llamadas** en la exploración de la izquierda y seleccione **Auto attendants** > **Agregar nuevo**.
  
Si desea más información sobre los operadores automáticos, consulte [¿Cuáles son los operadores de sistema de teléfono automáticos?](what-are-phone-system-auto-attendants.md)
  
## <a name="step-1---getting-started"></a>Paso 1: tareas iniciales

- Para poder crear y configurar los operadores automáticos, necesitará obtener o transferir su pago existente o el servicio gratuito números. Después de obtener los números de servicio gratuito o de pago, se mostrarán en el **Skype para el centro de administración de negocios** > **voz** > página de**números de teléfono** . Para obtener los números de servicio, vea [números de teléfono de servicio de obtención de Skype para empresas y equipos de Microsoft](getting-service-phone-numbers.md), o si desea transferir y el número de servicio existente, consulte [transferir números de teléfono para Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md). **Usuario (suscriptor)** no pueden asignarse a operadores automáticos. Si está fuera de los Estados Unidos, no puede utilizar el Skype para el centro de administración de negocios para obtener números de servicio; vaya [aquí](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar.
    
    > [!CAUTION]
    > Para obtener y utilizar los números de teléfono gratuitos, necesitará configurar comunicaciones créditos. Para ello, consulte [¿qué comunicaciones créditos?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) y [Configurar comunicaciones créditos para su organización](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md). 
  
- La organización debe tener (como mínimo) una licencia Enterprise E3 plus **Sistema de teléfono** o una licencia de Enterprise E5. El número de licencias de usuario de **Sistema telefónico** se asignan afecta a la cantidad de números de servicio que están disponibles para ser usados para operadores automáticos. Los números de los operadores automáticos que puede tener depende de las licencias de **Conferencias de Audio** y **Sistema de teléfono** número asignados en su organización. Para obtener más información acerca de licencias, vaya [aquí](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Para redirigir las llamadas a un operador o una opción de menú es un usuario con una licencia de **Sistema de teléfono** en línea, debe habilitarlos para Telefonía IP empresarial o llamar a los planes en Office 365 les asigne. Consulte [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). También puede utilizar Windows PowerShell. Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` 
  
## <a name="step-2---create-a-new-auto-attendant"></a>Paso 2: crear un operador automático nuevo

En el **Centro de administración de Skype Empresarial**, haga clic en **Enrutamiento de llamadas** > **Operadores automáticos**, y después en **Agregar nuevo**:
  
### <a name="edit-general-info-page"></a>Página Editar información general
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Nombre** Escriba un nombre descriptivo para el operador automático. El nombre es necesario y puede contener hasta 64 caracteres, incluidos espacios. Se enumerarán en la columna **nombre** de la ficha **operadores automáticos** .
***

![Número 2](../images/sfbcallout2.png)<br/>**Número de teléfono** Esta configuración es opcional. Si lo desea, seleccione un número de teléfono para el operador automático. Puede elegir cualquier pago de servicio disponible o número de teléfono gratuito que tiene para su organización. Si no aparece ningún número de teléfono, necesitará obtener un pago de servicio o teléfono gratuito número. Vaya [aquí](getting-service-phone-numbers.md) para obtenerlos. <br/> <br/>

    > [!Note]
    > **User (subscriber)** numbers can't be assigned to auto attendants.
***
![Número 3](../images/sfbcallout3.png)<br/>**Zona horaria**: debe establecer la zona horaria para el operador automático, pero no es necesario que se corresponda con la zona horaria de la dirección principal que se muestra para su organización. Cada operador automático puede tener una zona horaria diferente, y el horario laboral establecido para el operador automático se ajustará en función de la zona horaria seleccionada.
***
![14](../images/sfbcallout4.png)<br/>**Idioma** Seleccione el idioma que desea utilizar para el operador automático de cualquiera de los idiomas disponibles que se muestran. El idioma que se establece aquí es el idioma que utilizará el operador automático para interactuar con las personas que llaman a este operador automático y las instrucciones del sistema se reproducirá en este idioma.
***
![Número 5](../images/sfbcallout5.png)<br/>**Reconocimiento de voz** El reconocimiento de voz está disponible y si se selecciona esta opción. Las personas que llaman en pueden utilizar la entrada de voz en el idioma establecido. Puede deshabilitar el reconocimiento de voz desactivando si desea sólo permiten a los usuarios utilizar el teclado del teléfono.
***
![Número 6](../images/sfbcallout6.png)<br/>**Operador** Esto es opcional y no es necesario establecer para el operador automático. Sin embargo, puede establecer la opción de **operador** para las personas que llaman al ser capaz de interrumpir la ejecución de los menús para hablar con una persona que les ayude a. <br/> <br/> Automáticamente se asigna la tecla 0 a Operador. <br/> <br/> Si se configura esto, necesitará decirle a la gente a quién llamar en que ésta es una opción disponible en **Editar las opciones de menú** en la página de **control horario de las llamadas** . Si define un operador en el operador automático, debe escribir el texto del mensaje correspondiente en el cuadro **escucharán** o cambiar el archivo de audio para incluir esta opción. Por ejemplo, "para el operador, presione cero." <br/><br/>  Puede elegir entre las siguientes opciones para designar un operador: 
*    **Persona de la empresa** con una licencia de **Sistema de teléfono** que está habilitada para la Telefonía IP empresarial o asignada llamando a planes de Office 365. <br/>

        > [!Note] 
        > **Persona de la empresa** puede ser un usuario en línea o un usuario alojados en instalaciones con Skype para Business Server 2015 o Lync Server 2013. Lync Server 2010 no es compatible. <br/> 

*    **Llame a la cola** que ha configurado. 
*    Puede configurar, por lo que la persona que llama se enviarán al correo de voz. Para ello, seleccione la **persona de la empresa** y establecer llamadas de esta persona para reenviarse directamente al correo de voz. 
   
### <a name="select-hours-of-operation-page"></a>Página Seleccionar horas de funcionamiento

De forma predeterminada, horario se establecen en 24 horas al día, 7 días a la semana, por lo que todas las horas se consideran horas de negocios. Todas las horas que no se incluyen en horario laboral se consideran después del horario laboral. Si selecciona la opción **personalizada** y definir las horas de negocios, a continuación, una nueva página denominada **después de control de horas de las llamadas** se agregará donde puede configurar la llamada tratamiento para después del horario laboral para el operador automático.
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Número 1](../images/sfbcallout1.png)<br/>Seleccione la opción **Personalizado** para seleccionar horas laborales específicas en el calendario. Al seleccionar **Personalizado**, el horario laboral se ajusta de forma predeterminada al intervalo de lunes a viernes, de 9:00 a 17:00.  
***
![Número 2](../images/sfbcallout2.png)<br/>Para cambiar el horario de oficina, resalte el horario que desea establecer con el calendario. El calendario permite seleccionar el horario en intervalos de 30 minutos y el horario que seleccione aquí se establecerá en función de la zona horaria que establezca en la página **información General** . Para configurar un salto (un almuerzo, por ejemplo), anule la selección o arrastre para anular la selección de la hora en el calendario. Puede establecer varios saltos dentro del horario laboral. 
   
### <a name="select-business-hours-call-handling-page"></a>Seleccione horario de llamar a la página de control

> [!TIP]
> Si utiliza una programación personalizada para el horario laboral, también deberá configurar la administración de llamadas para las horas fuera del horario laboral. Para que pueda establecer los ajustes correspondientes, se agregará una página **Administración de llamadas fuera del horario laboral**, donde encontrará las mismas opciones que en **Administración de llamadas en horario laboral**. 
  
Puede configurar saludos, mensajes y menús que la gente que escuchará llamada al número de teléfono de operador automático de la organización durante el horario laboral.
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Saludo de la empresa** Saludo de horario comercial es opcional y puede establecerse en **None**. En este caso, el llamador no escuchará ningún mensaje o saludo antes de la llamada se controla mediante una de las opciones que seleccione. También puede cargar un archivo de audio (en formatos WAV, mp3 o .wma), o crear un saludo personalizado con texto a voz.
*    **Ninguno** Ningún saludo se reproducirá cuando le llamen al número de teléfono de operador automático.
*    **Crear una personalizada de saludo** Si elige esta opción, escriba el texto que desea que el sistema lea (hasta 1000 caracteres). Por ejemplo, puede escribir "Bienvenidos a Contoso. Su llamada es importante para nosotros." en el cuadro **escucharán** .
*    **Cargar un archivo de audio** Si selecciona esta opción, grabar el saludo y, a continuación, cargar el archivo de audio (en un formato .wav,. mp3 o .wma).
***
![Número 2](../images/sfbcallout2.png)<br/>Puede seleccionar qué ocurre con las llamadas que llegan durante el horario laboral. Puede elegir entre las siguientes opciones:
*    **Desconectar** Si se selecciona, la persona que llama se desconectará después de escuchar un saludo de horario comercial.
*    **Redirigir la llamada** Esto puede utilizarse para enviar automáticamente la llamada al:
     *    **Persona de la empresa** con una licencia de **Sistema de teléfono** que está habilitada para la Telefonía IP empresarial o asignada llamando a planes de Office 365. Puede configurar, por lo que la persona que llama se puede enviar al correo de voz. Para ello, seleccione la **persona de la empresa** y establezca esta persona para que las llamadas se desvían directamente al correo de voz. <br/><br/>   
        > [!Note]
        > **Persona de la empresa** puede ser un usuario en línea o un usuario alojados en instalaciones con Skype para Business Server 2015 o Lync Server 2013. Lync Server 2010 no es compatible. <br/><br/>

     *    Una **Cola llame** mediante una cola llamar permite que la llamada se transfiera a una cola existente llame que ha configurado.
     *    Auto operador para crear un segundo nivel de opciones de menú que contiene un submenú otro **operador automático** , puede utilizar una existente. Se denominan a operadores automáticos anidados.
*    **Reproducir mensaje de opciones de menú** Éstos también pueden utilizarse para permitirle configurar un mensaje de solicitud que desea reproducir.
***
![Número 3](../images/sfbcallout3.png)<br/>**Texto del menú**: para crear un mensaje para el menú principal puede usar la característica Texto a voz o cargar un archivo de audio (.wav, .mp3 o .wma). Puede escribir el mensaje en el cuadro **Las personas que llaman escucharán** o grabar un archivo de audio y decir, por ejemplo: "Pulse o diga 1 para Ventas. Pulse o diga 2 para Servicios. Pulse o diga 3 para Atención al cliente. Para hablar con el operador, pulse o diga 0. Para escuchar este mensaje de nuevo, pulse la tecla de asterisco o diga Repetir". **Crear un mensaje de asistencia por voz personalizado**: si elige esta opción, debe introducir el texto que desea que lea el sistema (hasta 1000 caracteres). **Cargar un archivo de audio**: si elige esta opción, deberá grabar el saludo y cargar el archivo de audio (en formato .wav, .mp3 o .wma).
***
![Número 4](../images/sfbcallout4.png)<br/>**Marcado por nombre** Si elige esta opción, esto permitirá que las personas que llaman a buscar personas en su organización mediante la búsqueda en el directorio. Puede seleccionar qué personas aparecerá como disponible o no está disponible para hacer llamadas por su nombre mediante la configuración de las opciones en la página **ámbito de marcado** . Cualquier usuario con una licencia de **Sistema de teléfono** en línea o cualquier usuario alojadas en locales utilizando Skype para Business Server 2015 o Lync Server 2013, puede encontrarse con marcado por su nombre.<br/><br/>  **Precaución:** Los usuarios alojados en instalaciones con Lync 2010 **no se puede llegar** con marcado por su nombre.
***

![Número 5](../images/sfbcallout5.png)<br/>**Editar las opciones de menú** Opciones de menú se pueden agregar o eliminar mediante botones de teclas en el teclado numérico. Para agregar una opción de menú, presione la tecla correspondiente en el teclado numérico. Las claves en uso cambiará de color y aparece debajo de la fila correspondiente de opciones. Para eliminar una opción de menú, haga clic en la clave correspondiente en el control de teclado para anular la selección de esta clave. Se quitará la fila de asignación de claves.<br/><br/>  **Sugerencia:** Tendrá que actualizar el texto de mensajes de menú o volver a grabar el audio por separado al agregar a quitar opciones porque no se efectuará automáticamente para el aviso de menú existente.  <br/><br/>  Cualquier opción de menú se puede agregar y quitar en cualquier orden, y las asignaciones de teclas no tienen que ser continua. Es posible, por ejemplo, para crear un menú con las teclas 0, 1 y 3 asignado a opciones, mientras no se utiliza la clave 2.<br/><br/> 

    > [!Note] 
    > The keys * (Repeat) and # (Back) are reserved by the system and can't be reassigned. If speech recognition is enabled, pressing * will correspond with "Repeat" and # will correspond with the "Back" voice commands. <br/><br/>

Para configurar las opciones de menú, después de seleccionar las claves, necesitará: 
- **Escriba el nombre de la opción** Esto puede tener hasta 64 caracteres y puede contener varias palabras como "Servicio al cliente" o "operaciones y motivos". Si está habilitado el reconocimiento de voz, automáticamente se reconocerá el nombre y la persona que llama será capaz, presione 3, diga "tres" o diga "Customer Service" para seleccionar la opción asignada en la clave 3. 
- El siguiente paso es seleccionar dónde está la llamada a enviarse si se presiona la tecla correspondiente, o se selecciona la opción Usar reconocimiento de voz. La llamada puede enviarse a: 
    - **Operador** Si el operador ya está configurado, se asigna automáticamente a la clave 0, pero también se puede eliminar o reasignar a una clave distinta. Si el operador no tiene ninguna clave, el comando de voz "Operador" se deshabilitará demasiado. 
    - Una **persona de la empresa** con una licencia de **Sistema de teléfono** que está habilitada para la Telefonía IP empresarial o asignada a un Plan de llamadas en Office 365. Puede configurar, por lo que la persona que llama se puede enviar al correo de voz. Para ello, seleccione la **persona de la empresa** y establezca esta persona para que las llamadas se desvían directamente al correo de voz.<br/><br/> 
    
        > [!Note] 
        > **Persona de la empresa** puede ser un usuario en línea o un usuario alojados en instalaciones con Skype para Business Server 2015 o Lync Server 2013. Lync Server 2010 no es compatible. <br/><br/>

    - **Llame a la cola** Utilizando una opción de cola de llamada permite que la llamada se transfiera a una cola de llamada existente que ha configurado. 
    - **Operador automático** Puede utilizar a un operador automático existente para crear un segundo nivel de opciones de menú que contiene un submenú. Se denominan a operadores automáticos anidados.<br/><br/>
    
        > [!Note]
        > El **horario** de operadores automáticos anidados (o de segundo nivel) también se utilizará, incluido para las llamadas enviadas desde otros operadores automáticos que se han configurado.         
   
### <a name="select-holidays-page"></a>Seleccione página de días festivos 

Puede agregar hasta 20 días festivos programadas a cada operador automático.
  
![Configuración de días festivos en el operador automático](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Agregar un día festivo** Escriba un nombre para tus vacaciones nuevo en el campo **nombre del día festivo** .<br/><br/> Nombres de festividades pueden constar de un máximo de 64 caracteres y deben ser únicos para el mismo operador automático. Por ejemplo, no puede tener dos días festivos denominados "Navidad" en el mismo operador automático.  
***
![Número 2](../images/sfbcallout2.png)<br/>**Felicitación de Navidad** El saludo de vacaciones es opcional y puede establecerse en **None**. En este caso, el llamador no escuchará ningún mensaje o saludo antes de la llamada se controla mediante una de las opciones que seleccione. También puede cargar un archivo de audio (en formatos WAV, mp3 o .wma), o crear un saludo personalizado con texto a voz.
*    **Ninguno** Ningún saludo se reproducirá cuando le llamen al número de teléfono de operador automático.
*    **Crear una personalizada de saludo** Si elige esta opción, escriba el texto que desea que el sistema lea (hasta 1000 caracteres). ¡Por ejemplo, puede escribir "feliz año nuevo! Nuestras oficinas están cerrados." en el cuadro **escucharán** .
*    **Cargar un archivo de audio** Si selecciona esta opción, grabar las vacaciones y, a continuación, cargar el archivo de audio (en un formato .wav,. mp3 o .wma).  
***
![Número 3](../images/sfbcallout3.png)<br/>**¿Qué ocurre con las llamadas tras el saludo?** Puede seleccionar qué ocurre con las llamadas que llegan durante esta Navidad. Puede elegir entre las siguientes opciones:
*    **Desconectar** La persona que llama se desconectará después de escuchar la felicitación en fechas señaladas.
*    **Redirigir la llamada** Esto puede utilizarse para enviar automáticamente la llamada al:
     *    Una **persona de la empresa** con una licencia de **Sistema de teléfono** que está habilitada para la Telefonía IP empresarial o asignada llamando a planes de Office 365. Puede configurar, por lo que la persona que llama se puede enviar al correo de voz. Para ello, seleccione la **persona de la empresa**y establezca esta persona para que las llamadas se desvían directamente al correo de voz. <br/><br/> 
     
         > [!Note] 
         > **Persona de la empresa** puede ser un usuario en línea o un usuario alojados en instalaciones con Skype para Business Server 2015 o Lync Server 2013. Lync Server 2010 no es compatible.<br/><br/>

     *    **Llame a la cola** para transferir la llamada a una cola existente llame que ha configurado.
     *    Otro **operador automático**, para crear un segundo nivel de opciones de menú que contiene un submenú. Se denominan a operadores automáticos anidados. <br/><br/>
     
         > [!Note]
         > De forma predeterminada, se establecen todas las llamadas que llegan durante un período de vacaciones se desconecta después de saludo (si existe), por lo que debe especificar una redirección si se desea un comportamiento diferente.

***
![Número 4](../images/sfbcallout4.png)<br/>**¿Cuándo desea que las vacaciones para iniciar y finalizar?** Escriba la fecha de comienzo del día festivo en formato mm/dd/aaaa y, a continuación, seleccione una hora de inicio, fecha final y hora final, cuando se le indique en la tabla del intervalo de fecha.<br/><br/>Puede especificar hasta 10 diferentes rangos de fecha para un día festivo. Por ejemplo, podría agregar intervalos de fechas para las vacaciones de año nuevo hasta 10 años. Un día festivo puede abarcar varios días.<br/><br/>Para agregar nuevas fecha vacaciones intervalos (por ejemplo, para el próximo año), haga clic en **Agregar otro**y, a continuación, escriba un nuevo conjunto de fechas de inicio y finalización para las vacaciones.<br/><br/>También se admiten días festivos anidados. Por ejemplo, puede anidar múltiples vacaciones dentro de un marco de tiempo de "vacaciones": 
*    **El 24 de diciembre hasta el 3 de enero:** "¡Felices fiestas! Nuestras oficinas están cerrados. Se reabrirá el 4 de enero."
*    **25 de diciembre:** "¡Feliz Navidad! Nuestras oficinas están cerrados. Se reabrirá el 4 de enero."
*    **El 1 de enero:** "Feliz año nuevo! Nuestras oficinas están cerrados. Se reabrirá el 4 de enero."
   
Después de guardar al operador automático, los días festivos aparecen en la ficha de **vacaciones** , donde puede editar, agregar o modificar la configuración de vacaciones.
  
### <a name="select-dial-scope-page"></a>Página Seleccionar ámbito de marcado

En esta página, puede configurar qué usuarios de la organización serán enumerados en su directorio y disponibles para marcado por nombre cuando una persona que llama para su organización.
  
![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>La opción **Incluir** ofrece dos posibilidades:
*    **En línea todos los usuarios** Esta opción permitirá todas las personas de la organización que desea incluir en la búsqueda de directorio. Todos los usuarios en línea con una licencia de **Sistema de teléfono** , así como los usuarios alojados en locales utilizando Skype para Business Server 2015 o Lync Server 2013 que tengan planes de llamada Office 365, se enumerarán. 
*    **Personalizado** Si utiliza esta opción, puede buscar un grupo de Office 365, lista de distribución o grupo de seguridad que se ha creado en su organización y las personas que incluyan en este grupo de Office 365, lista de distribución o grupo de seguridad que son ambos **usuarios en línea con un Licencia de sistema de teléfono** o alojado en instalaciones con Skype para Business Server 2015 o Lync Server 2013. Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad. <br/><br/> 

    > [!Caution]
    > Usuarios locales de las implementaciones de Lync Server 2010 no aparecerá cuando alguien busca en el directorio utilizando el marcado por su nombre. 
***
![Número 2](../images/sfbcallout2.png)<br/>Con la opción de **Excluir** , tiene dos opciones:
*    **Ninguno**: esta opción indica que no se debe excluir a ningún usuario de la búsqueda en directorios. 
*    **Personalizado** Si utiliza esta opción, puede buscar un grupo de Office 365, lista de distribución o grupo de seguridad que se ha creado en su organización, y todas las personas se agregan a este grupo de Office 365, lista de distribución o grupos de seguridad se excluirán de la búsqueda en el directorio. Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad. <br/><br/> 

    > [!Caution]
    > Usuarios locales de las implementaciones de Lync Server 2010 no aparecerá cuando alguien busca en el directorio utilizando el marcado por su nombre.          
   
> [!NOTE]
> Puede tardar hasta 36 horas para un nuevo usuario para que su nombre aparezca en el directorio cuando alguien utiliza marcado por su nombre con el reconocimiento de voz. 
  
Después de introducir todos los campos necesarios y configurar menús y opciones de manejo de llamadas, haga clic en **Guardar**.
  
## <a name="editing-and-testing-auto-attendants"></a>Edición y pruebas a operadores automáticos

Después de haber guardado al operador automático, se enumerarán en la página de **operadores automáticos** . Esto le permitirá ver rápidamente algunas de las opciones que ha configurado, incluidos el nombre, número de teléfono, idioma y estado.
  
Si desea realizar cambios en el operador automático, seleccionar al operador automático y, a continuación, en el panel Acción, haga clic en **Editar**.
  
Puede colocar una llamada de prueba a su operador automático también rápidamente mediante el botón **de prueba** en el panel de acción.
  
## <a name="want-to-know-more"></a>¿Desea obtener más información?

También puede usar Windows PowerShell para crear y configurar operadores automáticos.
  
### <a name="auto-attendant-cmdlets"></a>Cmdlets para operadores automáticos

Estos son los cmdlets que necesita para administrar un operador automático.
  
||| 
|---|---|
[Nueva CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796493.aspx)                                                                      | [Nueva CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/en-us/library/mt796484.aspx)                                                              |
| [Conjunto de CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796486.aspx)                                                                      | [Nueva CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/en-us/library/mt796485.aspx)                                                           |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796482.aspx)                                                                      | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/en-us/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)       |
| [Quitar CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796492.aspx)                                                                   | [Nueva CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/en-us/library/mt796488.aspx)                                                                  |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/en-us/library/mt796479.aspx)                                                                                 | [Nueva CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/en-us/library/mt796489.aspx)                                                              |
| [CsOrganizationalAutoAttendantHolidays de exportación](https://docs.microsoft.com/en-us/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [Nueva CsOnlineTimeRange](https://technet.microsoft.com/en-us/library/mt796491.aspx)                                                                                  |
| [Nueva CsOnlineDateTimeRange](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                                       | [Nueva CsOnlineSchedule](https://technet.microsoft.com/en-us/library/mt796490.aspx)                                                                                   |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/en-us/library/mt796483.aspx)                                                     | [Nueva CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/en-us/library/mt796487.aspx)                                               |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/en-us/library/mt796481.aspx)                                                     | [CsOrganizationalAutoAttendantHolidays de importación](https://docs.microsoft.com/en-us/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [Nueva CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/en-us/library/mt796480.aspx)                                                      |  |   |
   
### <a name="more-about-windows-powershell"></a>Más información sobre Windows PowerShell

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Temas relacionados
[Aquí está lo que se obtiene con el sistema de teléfono en Office 365](here-s-what-you-get-with-phone-system.md)

[Obtener números de teléfono de servicio Skype para empresas y Teams de Microsoft](getting-service-phone-numbers.md)

[Disponibilidad de país y región para conferencias de Audio y planes de llamada](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    

