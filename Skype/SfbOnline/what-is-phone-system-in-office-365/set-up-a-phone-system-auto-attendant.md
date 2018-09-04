---
title: Configurar un operador automático de sistema telefónico
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Aprenda cómo configurar y probar operadores automáticos de sistema telefónico (PBX en la nube) para administrar eficazmente las llamadas en su organización. '
ms.openlocfilehash: fb35e36e7d59a3d47584fd15e592f68dd3ac4ae5
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780467"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Configurar un operador automático de sistema telefónico

Los operadores automáticos permiten que las personas que llaman a su organización naveguen por un sistema de menús para acceder al departamento, la cola de llamadas, la persona o el operador correctos. Puede crear un operador automático para su organización usando el Centro de administración de Skype for Business. Para crear un operador automático nuevo, vaya a **Enrutamiento de llamadas** en el panel de navegación izquierdo y seleccione **Operadores automáticos** > **Agregar nuevo**.
  
Si desea obtener más información sobre los operadores automáticos, consulte [¿Qué son los operadores automáticos de sistema telefónico?](/microsoftteams/what-are-phone-system-auto-attendants)
  
## <a name="step-1---getting-started"></a>Paso 1: Tareas iniciales

- Antes de crear y configurar los operadores automáticos, necesitará obtener o transferir sus números de servicio existentes de pago o gratuitos. Después de obtener los números de servicio de pago o gratuitos, se mostrarán en la página **Centro de administración de Skype for Business** > **Voz** > **Números de teléfono**. Para obtener sus números de servicio, vea [Obtener números de teléfono de servicio para Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)o, si desea transferir un número de servicio existente, vea [Transferir los números de teléfono a Office 365](/microsoftteams/transfer-phone-numbers-to-office-365). No se pueden asignar números de **usuario (suscriptor)** a operadores automáticos. Si está fuera de los Estados Unidos, no puede usar el centro de administración de Skype for Business para obtener números de servicio; vaya [aquí](/microsoftteams/manage-phone-numbers-for-your-organization) en su lugar.
    
    > [!CAUTION]
    > Para obtener y usar los números de teléfono gratuitos, necesita configurar créditos de comunicaciones. Para ello, consulte [¿Qué son los créditos de comunicaciones?](/microsoftteams/what-are-communications-credits) y [Configurar créditos de comunicaciones para su organización](/microsoftteams/set-up-communications-credits-for-your-organization). 
  
- Su organización debe tener (como mínimo) una licencia de **Sistema telefónico** Enterprise E3 plus o una licencia Enterprise E5. El número de licencias de usuario de **Sistema telefónico** que se asignan afecta al número de números de servicio que están disponibles para usarse en operadores automáticos. Los números de los operadores automáticos que puede tener depende del número de licencias de **sistema telefónico** y **audioconferencia** asignadas en la organización. Para obtener más información acerca de las licencias, vaya [aquí](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Para redirigir las llamadas a un operador o una opción de menú que sea un usuario en línea con una licencia de **sistema telefónico**, debe habilitarlos para Enterprise Voice o asignarles planes de llamadas en Office 365. Vea [Asignar licencias de Skype for Business y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). También puede usar Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` 
  
## <a name="step-2---create-a-new-auto-attendant"></a>Paso 2: Crear un operador automático nuevo

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usando el centro de administración de Skype for Businessl**


En el **Centro de administración de Skype Empresarial**, haga clic en **Enrutamiento de llamadas** > **Operadores automáticos**, y después en **Agregar nuevo**:
  
### <a name="edit-general-info-page"></a>Página Editar información general
  
![Página 1 de Nuevo operador automático.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Nombre**: Escriba un nombre para mostrar descriptivo para el operador automático. El nombre es obligatorio, y puede contener hasta 64 caracteres, espacios incluidos. Se enumerará en la columna **Nombre** en la ficha **Operadores automáticos**.
***

![Número 2](../images/sfbcallout2.png)<br/>**Número de teléfono** Esta configuración es opcional. Si lo desea, seleccione un número de teléfono para el operador automático. Puede seleccionar cualquier número de teléfono de servicio gratuito o de pago disponibles que tenga para su organización. Si no se enumera ningún número de teléfono, deberá obtener un número de servicio de pago o gratuito. Vaya [aquí](getting-service-phone-numbers.md) para obtenerlos. <br/> <br/>

> [!NOTE]
> No se pueden asignar números de **usuario (suscriptor)** a operadores automáticos.
    
***
![Número 3](../images/sfbcallout3.png)<br/>**Zona horaria**: debe establecer la zona horaria para el operador automático, pero no es necesario que se corresponda con la zona horaria de la dirección principal que se muestra para su organización. Cada operador automático puede tener una zona horaria diferente, y el horario laboral establecido para el operador automático se ajustará en función de la zona horaria seleccionada.
***
![14](../images/sfbcallout4.png)<br/>**Idioma**: Seleccione el idioma que quiere usar para su operador automático de entre los idiomas disponibles enumerados. El idioma que defina aquí será el idioma que usará el operador automático para interaccionar con los autores de las llamadas que este reciba. Todos los mensajes del sistema se reproducirán en este idioma.
***
![Número 5](../images/sfbcallout5.png)<br/>**Reconocimiento de voz**: El reconocimiento de voz es una opción disponible que, si se activa, permite que los autores de llamadas usen la voz en el idioma que especifique. Puede desactivar el reconocimiento de voz borrando la marca de esta opción si desea que las personas utilicen solo el teclado del teléfono.
***
![Número 6](../images/sfbcallout6.png)<br/>**Operador**: Este ajuste es opcional y no es necesario activarlo para el operador automático. Sin embargo, puede establecer la opción **Operador** para que los autores de llamadas puedan salir de los menús para hablar con una persona que les proporcione asistencia. <br/> <br/> Automáticamente se asigna la tecla 0 al operador. <br/> <br/> Si configura esta opción, también deberá informar a los autores de llamadas de su disponibilidad en **Editar las opciones de menú** en la página **Administración de llamadas en horario comercial**. Si define un operador para su operador automático, deberá introducir el texto del mensaje correspondiente en el cuadro **Las personas que llaman escucharán** o cambiar el archivo de audio para incluir esta opción. Por ejemplo, "Para hablar con el operador, pulse cero." <br/><br/>  Puede elegir entre las siguientes opciones para designar un operador: 
*    **Persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a planes de llamadas en Office 365. <br/>

        > [!Note] 
        > La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013. Lync Server 2010 no es compatible. <br/> 

*    Una **cola de llamadas** que haya creado. 
*    Puede establecer que el autor de la llamada se derive a un correo de voz. Para hacerlo, seleccione una **persona de su empresa** y establezca que las llamadas de esta persona se desvíen directamente al correo de voz. 
   
### <a name="select-hours-of-operation-page"></a>Página Seleccionar horas de funcionamiento

De manera predeterminada el horario comercial está configurado en 24 horas al día, los 7 días de la semana, por lo que todas las horas se consideran laborales. Todas las horas que no se incluyan en el horario comercial se consideran no laborales. Si selecciona la opción **Personalizado** y ajusta su horario comercial, se agregará una nueva página llamada **Administración de llamadas fuera del horario comercial** y tendrá que configurar la administración de llamadas recibidas fuera del horario comercial para el operador automático.
  
![Horas de operación del nuevo operador automático.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Número 1](../images/sfbcallout1.png)<br/>Seleccione la opción **Personalizado** para seleccionar horas laborales específicas en el calendario. Al seleccionar **Personalizado**, el horario laboral se ajusta de forma predeterminada al intervalo de lunes a viernes, de 9:00 a 17:00.
***
![Número 2](../images/sfbcallout2.png)<br/>Para cambiar el horario comercial, resalte el horario comercial que desea establecer con el calendario. El calendario le permite seleccionar el horario comercial en intervalos de 30 minutos, y el horario que seleccione aquí se basará en la zona horaria que haya configurado en la página **Información general**. Para configurar un descanso (almuerzo, por ejemplo), anule la selección o arrastre para anular la selección de la hora en el calendario. Puede establecer varios descansos dentro del horario comercial. 
   
### <a name="select-business-hours-call-handling-page"></a>Página de gestión de las llamadas Selección de horario comercial

> [!TIP]
> Si utiliza una programación personalizada para el horario laboral, también deberá configurar la administración de llamadas para las horas fuera del horario laboral. Para que pueda establecer los ajustes correspondientes, se agregará una página **Administración de llamadas fuera del horario laboral**, donde encontrará las mismas opciones que en **Administración de llamadas en horario laboral**. 
  
Puede configurar los saludos, los mensajes y los menús que escucharán las personas que contacten con el operador automático de su organización durante el horario laboral.
  
![Gestión de llamadas de horario comercial.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Saludo de la compañía** El saludo en horario comercial es opcional y puede establecerse en **Ninguno**. En este caso, el autor de la llamada no escuchará ningún mensaje o saludo antes de que la llamada se gestione mediante una de las opciones que seleccione. También puede cargar un archivo de audio (en formatos .wav, .mp3 o .wma), o crear un saludo personalizado usando texto a voz.
*    **Ninguno** No se reproducirá ningún saludo cuando las personas llamen al número de teléfono de operador automático.
*    **Crear un saludo personalizado**  Si elige esta opción, escriba el texto que desea que el sistema lea (hasta 1000 caracteres). Por ejemplo, puede escribir "Bienvenidos a Contoso. Su llamada es muy importante para nosotros." en el cuadro **Los autores de llamadas escucharán**.
*    **Cargar un archivo de audio**: Si elige esta opción, grabe el saludo y cargue el archivo de audio (en formato .wav, .mp3 o .wma).
***
![Número 2](../images/sfbcallout2.png)<br/>Puede seleccionar lo que ocurre con las llamadas que se reciben durante el horario comercial. Puede elegir entre las siguientes opciones:
*    **Desconectar** Si se selecciona, la persona que llama sera desconectada tras escuchar un saludo de horario comercial.
*    **Redirigir llamada** Esto puede usarse para enviar automáticamente la llamada a:
     *    **Persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a planes de llamadas en Office 365. Puede establecer que el autor de la llamada se derive a un correo de voz. Para hacerlo, seleccione una **persona de su empresa** y configúrela para que las llamadas que reciba esta persona se desvíen directamente al correo de voz. <br/><br/>   
        > [!Note]
        > La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013. Lync Server 2010 no se admite. <br/><br/>

     *    Una **cola de llamadas** Usar una cola de llamadas permite que la llamada se transfiera a una cola de llamadas existente que haya configurado.
     *    Otro **Operador automático** Puede utilizar un operador automático existente para crear un segundo nivel de opciones de menú que contenga un submenú. Estos se denominan a operadores automáticos anidados.
*    **Reproducir el mensaje de opciones de menú** Estos también pueden utilizarse para permitirle configurar un aviso que desee reproducir.
***
![Número 3](../images/sfbcallout3.png)<br/>**Texto del menú**: para crear un mensaje para el menú principal puede usar la característica Texto a voz o cargar un archivo de audio (.wav, .mp3 o .wma). Puede escribir el mensaje en el cuadro **Las personas que llaman escucharán** o grabar un archivo de audio y decir, por ejemplo: "Pulse o diga 1 para Ventas. Pulse o diga 2 para Servicios. Pulse o diga 3 para Atención al cliente. Para hablar con el operador, pulse o diga 0. Para escuchar este mensaje de nuevo, pulse la tecla de asterisco o diga Repetir". **Crear un mensaje de asistencia por voz personalizado**: si elige esta opción, debe introducir el texto que desea que lea el sistema (hasta 1000 caracteres). **Cargar un archivo de audio**: si elige esta opción, deberá grabar el saludo y cargar el archivo de audio (en formato .wav, .mp3 o .wma).
***
![Número 4](../images/sfbcallout4.png)<br/>**Marcado por nombre** Si elige esta opción, esto permitirá a las personas que llaman buscar personas en su organización usando la búsqueda en el directorio. Puede seleccionar qué personas se mostrarán como disponibles o no disponibles para el marcado por nombre mediante la configuración de esas opciones en la página **Ámbito de marcado**. Cualquier usuario en línea con una licencia de **sistema telefónico** o cualquier usuario hospedado localmente utilizando Skype for Business Server 2015 o Lync Server 2013, puede encontrarse con el marcado por nombre.<br/><br/>  

> [!WARNING]
> Los usuarios alojados en implementaciones locales con Lync 2010 **no se pueden alcanzar** con marcado por nombre.
***

![Número 5](../images/sfbcallout5.png)<br/>**Editar las opciones de menú** Puede agregar o eliminar opciones de menú usando las teclas del teclado. Para agregar una opción de menú, pulse la tecla correspondiente en el teclado. Las teclas en uso cambiarán de color y la línea de opciones correspondiente se mostrará debajo. Para eliminar una opción de menú, pulse la tecla adecuada en el control del teclado para eliminar la selección de esa tecla. Se quitará la fila de asignación de teclas.<br/><br/>  **Sugerencia:** Deberá actualizar los textos de los avisos de los menús o volver a grabar el audio por separado cuando se agregue a la eliminación de opciones porque no se realiza automáticamente para el aviso de menú existente.  <br/><br/>  Puede agregar y eliminar cualquier opción de menú en cualquier orden; las teclas asignadas no tienen que ser sucesivas. Es posible, por ejemplo, crear un menú con las teclas de 0, 1 y 3 que se asignan a opciones, mientras que no se usa la tecla 2.<br/><br/> 

> [!NOTE]
> Las teclas * (Repetir) y # (Atrás) están reservadas por el sistema y no se pueden reasignar. Si el reconocimiento de voz está activado, pulsar * equivaldrá al comando de voz "Repetir" y # a "Volver".


Para configurar las opciones de menú, después de seleccionar la(s) tecla(s), necesitará: 
- **Escribir el nombre de la opción** Este puede tener hasta 64 caracteres y puede contener varias palabras como "Servicio de asistencia al cliente" u "Operaciones y motivos". Si está habilitado el reconocimiento de voz, automáticamente se reconocerá el nombre y la persona que llama podrá, o bien presionar 3, decir "tres" o decir "servicio de asistencia al cliente" para seleccionar la opción asignada a la tecla 3. 
- El siguiente paso es seleccionar donde se envía la llamada si se presiona la tecla correspondiente, o está seleccionada la opción Usar reconocimiento de voz. La llamada se puede enviar al: 
    - **Operador** Si el operador ya está configurado, se asigna automáticamente a la tecla 0, pero también se puede eliminar o volverse a asignar a una tecla diferente. Si el operador no está establecido para alguna tecla, entonces el comando de voz "Operador" se deshabilitará también. 
    - **Persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a un plan de llamadas en Office 365. Puede establecer que el autor de la llamada se derive a un correo de voz. Para hacerlo, seleccione una **persona de su empresa** y configúrela para que las llamadas que reciba esta persona se desvíen directamente al correo de voz.<br/><br/> 
    
        > [!Note] 
        > La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013. Lync Server 2010 no se admite. <br/><br/>

    - **Cola de llamadas** Usar una cola de llamadas permite que la llamada se transfiera a una cola de llamadas existente que haya configurado. 
    - **Operador automático** Puede utilizar un operador automático existente para crear un segundo nivel de opciones de menú que contenga un submenú. Estos se denominan a operadores automáticos anidados.<br/><br/>
    
        > [!Note]
        > El **Horario comercial** de operadores automáticos anidados (o de segundo nivel) también se utilizará, lo que incluye las llamadas enviadas desde otros operadores automáticos que se hayan configurado.         
   
### <a name="select-holidays-page"></a>Página Selección de días festivos 

Puede agregar un máximo de 20 días festivos programados a cada operador automático.
  
![Configuración de días festivos en el operador automático](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Agregar días festivos** Escriba un nombre para su nuevo día festivo en el campo **Nombre de días festivos**.<br/><br/> Los nombres de días festivos pueden constar de hasta 64 caracteres y deben ser únicos para el mismo operador automático. Por ejemplo, no puede tener dos días festivos denominados "Navidad" en el mismo operador automático.  
***
![Número 2](../images/sfbcallout2.png)<br/>**Saludo de días festivos** El saludo de días festivos es opcional y puede establecerse en **Ninguno**. En este caso, el autor de la llamada no escuchará ningún mensaje o saludo antes de que la llamada se gestione mediante una de las opciones que seleccione. También puede cargar un archivo de audio (en formatos .wav, .mp3 o .wma), o crear un saludo personalizado usando texto a voz.
*    **Ninguno** No se reproducirá ningún saludo cuando las personas llamen al número de teléfono de operador automático.
*    **Crear un saludo personalizado**  Si elige esta opción, escriba el texto que desea que el sistema lea (hasta 1000 caracteres). Por ejemplo, puede escribir "¡Feliz año nuevo! Nuestras oficinas están cerradas en este momento". en el cuadro **Los autores de llamadas escucharán**.
*    **Cargar un archivo de audio**: Si elige esta opción, grabe el saludo de días festivos y cargue el archivo de audio (en formato .wav, .mp3 o .wma).  
***
![Número 3](../images/sfbcallout3.png)<br/>**¿Qué sucede con las llamadas después del saludo?** Puede seleccionar lo que ocurre con las llamadas que se reciben durante este día festivo. Puede elegir entre las siguientes opciones:
*    **Desconectar** La persona que llama será desconectada tras escuchar el saludo de días festivos.
*    **Redirigir llamada** Esto puede usarse para enviar automáticamente la llamada a:
     *    Una **persona de la empresa** con una licencia de **sistema de teléfono** que está habilitada para Enterprise Voice o asignada a planes de llamadas en Office 365. Puede establecer que el autor de la llamada se derive a un correo de voz. Para hacerlo, seleccione una **persona de su empresa** y configúrela para que las llamadas que reciba esta persona se desvíen directamente al correo de voz. <br/><br/> 
     
         > [!Note] 
         > La **persona de la empresa** puede ser un usuario en línea o un usuario hospedado localmente mediante Skype for Business Server 2015 o Lync Server 2013. Lync Server 2010 no se admite.<br/><br/>

     *    Una **cola de llamadas** para transferir la llamada a una cola de llamadas existente que haya configurado.
     *    Otro **operador automático**, para crear un segundo nivel de opciones de menú que contenga un submenú. Estos se denominan a operadores automáticos anidados. <br/><br/>
     
         > [!Note]
         > De forma predeterminada, todas las llamadas que llegan durante un período de días festivos se establecen en desconectar después de saludo (si hay alguno), por lo que debe especificar un redireccionamiento si se desea obtener un comportamiento diferente.

***
![Número 4](../images/sfbcallout4.png)<br/>**¿Cuándo desea que comiencen y terminen los días festivos?** Escriba la fecha de comienzo de los días festivos en formato dd/mm/aaaa y, a continuación, seleccione una hora de inicio, la fecha de finalización y la hora de finalización, tal y como se le solicite en la tabla de intervalo de fecha.<br/><br/>Puede especificar hasta 10 diferentes intervalos de fecha para días festivos. Por ejemplo, puede agregar intervalos de fechas de los días festivos de fin de año hasta un máximo de 10 años. Un día festivo puede abarcar varios días.<br/><br/>Para agregar más intervalos de fecha de días festivos (por ejemplo, para el próximo año), haga clic en **Agregar otro**y, a continuación, escriba un nuevo conjunto de las fechas de inicio y finalización para los días festivos.<br/><br/>También se admiten días festivos anidados. Por ejemplo, puede anidar varios festivos dentro de un marco de tiempo "días festivos de descanso": 
*    **Del 24 de diciembre al 3 de enero:** "¡Felices vacaciones! Nuestras oficinas están cerradas en este momento. Volveremos a abrir el 4 de enero".
*    **El 25 de diciembre:** "¡Feliz Navidad! Nuestras oficinas están cerradas en este momento. Volveremos a abrir el 4 de enero".
*    **El 1 de enero:** "¡Feliz año nuevo! Nuestras oficinas están cerradas en este momento. Volveremos a abrir el 4 de enero".
   
Después de guardar el operador automático, los días festivos aparecen en la ficha de **Días festivos**, donde puede editar, agregar o modificar la configuración de días festivos.
  
### <a name="select-dial-scope-page"></a>Página Seleccionar ámbito de marcado

En esta página puede configurar qué usuarios de su organización se deben enumerar en el directorio y estarán disponibles para marcado por nombre cuando una persona llame a su organización.
  
![Ámbito de marcado para buscar con nombre de marcado.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>La opción **Incluir** ofrece dos posibilidades:
*    **Total de usuarios en línea**: Esta opción le permite incluir a todas las personas de su organización en la búsqueda en directorios. Se enumerarán todos los usuarios en línea con una licencia de **sistema telefónico**, así como los usuarios hospedados localmente utilizando Skype for Business Server 2015 o Lync Server 2013 que tengan planes de llamada en Office 365. 
*    **Personalizado** Si utiliza esta opción, puede buscar un grupo de Office 365, lista de distribución o grupo de seguridad que se haya creado en la organización, y las personas que se agreguen a este grupo de Office 365, lista de distribución o grupo de seguridad que sean o bien **Usuarios en línea con un licencia de sistema telefónico** o bien hospedadas localmente mediante Skype for Business Server 2015 o Lync Server 2013. Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad. <br/><br/> 

    > [!Caution]
    > Los usuarios locales de las implementaciones de Lync Server 2010 no se muestran cuando alguien busca en el directorio mediante marcado por nombre. 
***
![Número 2](../images/sfbcallout2.png)<br/>Al usar la opción **Excluir**, tiene dos opciones:
*    **Ninguno**: Esta opción indica que no se debe excluir a ningún usuario de la búsqueda en directorios. 
*    **Personalizado** Si utiliza esta opción, puede buscar un grupo de Office 365, una lista de distribución o un grupo de seguridad ya existentes en su organización para que se excluya de la búsqueda en directorios a todas las personas que se encuentren en este grupo de Office, lista de distribución o grupo de seguridad. Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad. <br/><br/> 

    > [!Caution]
    > Los usuarios locales de las implementaciones de Lync Server 2010 no se muestran cuando alguien busca en el directorio mediante marcado por nombre.          
   
> [!NOTE]
> El nombre del nuevo usuario podría tardar hasta 36 horas en aparecer en el directorio cuando alguien use el marcado por nombre con reconocimiento de voz. 
  
Después de completar todos los campos necesarios y configurar los menús y las opciones de administración de llamadas, haga clic en **Guardar**.
  
## <a name="editing-and-testing-auto-attendants"></a>Editar y probar un operador automático

Después de guardar un operador automático, este se mostrará en la página **Operadores automáticos**. Esto le permitirá ver rápidamente algunas de las opciones que ha configurado, como el nombre, el número de teléfono, el idioma y el estado.
  
Si desea realizar cambios en un operador automático, seleccione al operador automático y, a continuación, en el Panel de acciones, haga clic en **Editar**.
  
Puede realizar rápidamente una llamada de prueba a su operador automático mediante el botón **Probar** del Panel de acciones.
  
## <a name="want-to-know-more"></a>¿Desea obtener más información?

También puede usar Windows PowerShell para crear y configurar operadores automáticos.
  
### <a name="auto-attendant-cmdlets"></a>Cmdlets para operadores automáticos

Estos son los cmdlets que necesita para administrar un operador automático.
  
||| 
|---|---|
[New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx)                                                                      | [New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx)                                                              |
| [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx)                                                                      | [New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx)                                                           |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx)                                                                      | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)       |
| [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx)                                                                   | [New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx)                                                                  |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx)                                                                                 | [New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx)                                                              |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [New-CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx)                                                                                  |
| [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                                       | [New-CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx)                                                                                   |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx)                                                     | [New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx)                                               |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx)                                                     | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx)                                                      |  |   |
   
### <a name="more-about-windows-powershell"></a>Más información sobre Windows PowerShell

- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See also
[Esto es lo que conseguirá con un sistema telefónico en Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obtener números de teléfono de servicio para Skype for Business y Microsoft Teams](getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
    
  
 
