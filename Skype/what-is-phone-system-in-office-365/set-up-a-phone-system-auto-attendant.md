---
title: "Configurar un operador automático de sistema telefónico"
ms.author: tonysmit
author: tonysmit
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c

description: "Learn how to set up and test Phone System (Cloud PBX) auto attendents for efficient call handling for your organization. "
---

# Configurar un operador automático de sistema telefónico

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Los operadores automáticos de permitan a las personas que llaman a su organización y navegar por un sistema de menús conseguirlas para el departamento correcto, llame a cola, la persona o el operador. Puede crear a un operador automático para la organización mediante la Skype centro de administración de la empresa. Para crear un nuevo operador automático, vaya a **enrutamiento de llamadas** en el panel de navegación izquierdo y, a continuación, seleccione **los operadores automáticos de** > **Agregar nuevo**.
  
Si desea obtener más información sobre los operadores automáticos, consulte [¿Cuáles son los operadores automáticos de sistema telefónico?](what-are-phone-system-auto-attendants.md).
  
## Paso 1: tareas iniciales

- Para poder crear y configurar los operadores automáticos, necesitará obtener o transferir su pago existente o un servicio gratuito números. Después de obtener los números de servicio gratuito o de pago, se mostrarán en la **Skype centro de administración de negocio** > **voz** > página de **números de teléfono**. Para obtener los números de servicio, vea [Obtener números de teléfono de servicio de Skype Empresarial](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md)o, si desea transferir y el número de servicio existente, consulte [Números de teléfono de transferencia a Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md). Números de **usuario (suscriptor)** no se pueden asignar a los operadores automáticos. Si está fuera de los Estados Unidos, no puede usar la Skype centro de administración de la empresa para obtener números de servicio; vaya[Administrar los números de teléfono de su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar.
    
    > [!CAUTION]
    > Para obtener y utilizar números de teléfono gratuitos, debe configurar créditos de comunicaciones. Para ello, consulte [¿Qué son créditos de comunicaciones?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) y[Configurar comunicaciones créditos para su organización](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md). 
  
- Licencia Enterprise E5 o una licencia Enterprise E3 plus **Sistema telefónico**, debe tener su organización (como mínimo). El número de licencias de usuario de **Sistema de teléfono** asignados afecta a la cantidad de números de servicio que están disponibles para usarse con operadores automáticos. Los números de los operadores automáticos que puede tener depende de las licencias de **Sistema telefónico** y **Conferencias de Audio de** número que se asignan en su organización. Para obtener más información sobre licencias, vaya[Skype para Business y Microsoft Teams licencias de complemento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Para desviar llamadas a un operador o una opción de menú que es un usuario en línea con una licencia de **Sistema telefónico**, necesitará habilitarlos para telefonía IP empresarial o asignarles llamar a los planes de Office 365. Vea [Asignar Skype para Business y Microsoft Teams licencias](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). También puede usar Windows PowerShell. Ejecutar por ejemplo:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`. 
  
## Paso 2: crear un operador automático nuevo

En el **Centro de administración de Skype Empresarial**, haga clic en **Enrutamiento de llamadas** > **Operadores automáticos**, y después en **Agregar nuevo**:
  
### Página Editar información general

En la página **Editar información general**:
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Nombre** Escriba un nombre descriptivo para el operador automático. El nombre es necesario y puede contener un máximo de 64 caracteres, incluidos los espacios. Se mostrará en la columna **nombre** de la pestaña de **operadores automáticos**.  <br/> |
|**2** <br/> |**Número de teléfono** Esta opción es opcional. Si lo desea, seleccione un número de teléfono para el operador automático. Puede seleccionar cualquier pago de servicio disponible o el número de teléfono gratuito que tiene para su organización. Si no hay ningún números de teléfono, debe obtener un pago de servicio o un teléfono gratuito número. Vaya[Obtener números de teléfono de servicio de Skype Empresarial](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) para acceder a ellos. <br/> > [!NOTE]> Los números de **Usuario (suscriptor)** no se pueden asignar a los operadores automáticos.          |
|**3** <br/> |**Zona horaria**: debe establecer la zona horaria para el operador automático, pero no es necesario que se corresponda con la zona horaria de la dirección principal que se muestra para su organización. Cada operador automático puede tener una zona horaria diferente, y el horario laboral establecido para el operador automático se ajustará en función de la zona horaria seleccionada.  <br/> |
|**4** <br/> |**Idioma** Seleccione el idioma que desee usar para el operador automático de cualquiera de los idiomas disponibles que se muestran. El idioma que defina aquí es el idioma que usará el operador automático para interactuar con las personas que llaman a este operador automático y las indicaciones de sistema se reproducirán en este idioma. <br/> |
|**5** <br/> |**Reconocimiento de voz** Reconocimiento de voz está disponible y si se selecciona esta opción. Personas que llaman en pueden usar la entrada de voz en el idioma. Puede deshabilitar el reconocimiento de voz desactivando si desea solo permitir a los usuarios usar el teclado del teléfono. <br/> |
|**6** <br/> |**Operador** Esto es opcional y no es necesario establecer para el operador automático. Sin embargo, puede establecer la opción de **operador** para las personas que llaman en puedan interrumpir los menús para hablar con una persona para ayudarlo a. <br/>  Automáticamente se asigna la tecla 0 a Operador. <br/>  Si configura esto, también debe informar quién en que se trata de una opción disponible en el **menú Opciones de edición** en la página de **administración de llamadas de horario comercial**. Si establece un operador en el operador automático, necesitará escriba el texto del mensaje correspondiente en el cuadro **escucharán las personas que llaman** o cambiar el archivo de audio para incluir esta opción. Por ejemplo, "para el operador, presione cero." <br/>  Puede elegir entre las siguientes opciones para designar un operador: <br/>  Una **persona de la empresa** con una licencia de **Sistema telefónico** que está habilitada para telefonía IP empresarial o asignada llamar a los planes de Office 365. <br/> > [!NOTE]> **Persona de su empresa** puede ser un usuario en línea o un usuario hospedado en local con Skype para empresarial Server 2015 o Lync Server 2013. Lync Server 2010 no es compatible.           Una **cola de llamadas** que haya creado. <br/>  Puede configurarlo para que la persona que llama se enviarán a correo de voz. Para ello, seleccione la **persona de su empresa** y establezca las llamadas se desvíen directamente al correo de voz de la persona. <br/> |
   
### Página Seleccionar horas de funcionamiento

De forma predeterminada, las horas de trabajo se establecen en 24 horas, los 7 días de la semana, por lo que todas las horas se consideran horario comercial. Todas las horas que no se incluyen en horario comercial se consideran después del horario laboral. Si selecciona la opción **personalizada** y establecer el horario laboral, a continuación, una nueva página denominada **después de administración de llamadas de horas** se agrega donde puede configurar la llamada tratamiento de después del horario laboral para el operador automático.
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)
  
|||
|:-----|:-----|
|**1** <br/> |Seleccione la opción **Personalizado** para seleccionar horas laborales específicas en el calendario. Al seleccionar **Personalizado**, el horario laboral se ajusta de forma predeterminada al intervalo de lunes a viernes, de 9:00 a 17:00.  <br/> |
|**2** <br/> |Para cambiar las horas de trabajo, resalte el horario laboral que desea establecer con el calendario. El calendario le permite seleccionar las horas de trabajo en intervalos de 30 minutos y el horario laboral que seleccione aquí se establecerá basándose en la zona horaria que ha configurado en la página **información General**. Para configurar un salto (almuerzo, por ejemplo), anule la selección o arrastre para anular la selección de la hora en el calendario. Puede establecer varios saltos en horario comercial.  <br/> |
   
### Seleccione las horas de trabajo llamar a la página de administración

> [!TIP]
> Si utiliza una programación personalizada para el horario laboral, también deberá configurar la administración de llamadas para las horas fuera del horario laboral. Para que pueda establecer los ajustes correspondientes, se agregará una página **Administración de llamadas fuera del horario laboral**, donde encontrará las mismas opciones que en **Administración de llamadas en horario laboral**. 
  
Puede configurar saludos, indicaciones y los menús que quienes llamada al número de teléfono de operador automático de su organización escucharán durante el horario laboral.
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
|||
|:-----|:-----|
|**1**|**Saludo de la empresa**: el saludo para el horario laboral es opcional y se puede ajustar en **Ninguno**. En este caso, el autor de la llamada no oirá ningún saludo antes de que una de las opciones seleccionadas administre la llamada. También puede cargar un archivo de audio (en formato .wav, mp3 o .wma) o crear un saludo personalizado usando la característica Texto a voz. **Ninguno** Saludo no se reproducirá cuando personas llaman al número de teléfono de operador automático. **Crear un personalizado de saludo** Si elige esta opción, escriba el texto que desea que el sistema lea (hasta 1000 caracteres). Por ejemplo, puede escribir "Bienvenido a Contoso. La llamada es importante para nosotros."en el cuadro **escucharán las personas que llaman**. **Cargar un archivo de audio** Si selecciona esta opción, grabar el saludo y, a continuación, cargue el archivo de audio (en un formato .wav,. mp3 o .wma).|
|**2**| Puede seleccionar qué ocurre con las llamadas que llegan durante el horario comercial. Puede elegir entre las siguientes opciones: **Desconectar**: si selecciona esta opción, la llamada se desconectará después de reproducir el saludo del horario laboral. **Redirigir llamada**: puede usar esta opción para enviar la llamada automáticamente a: **Persona de su empresa** con una licencia de **Sistema telefónico** que está habilitada para telefonía IP empresarial o asignada llamar a los planes de Office 365. Puede configurarlo para que la persona que llama se pueden enviar al correo de voz. Para ello, seleccione la **persona de su empresa** y establezca esta persona a sus llamadas reenvía directamente al correo de voz.> [!NOTE]> **Persona de su empresa** puede ser un usuario en línea o un usuario hospedado en local con Skype para empresarial Server 2015 o Lync Server 2013. Lync Server 2010 no es compatible.           Una **cola de llamadas**: esta opción le permite transferir la llamada a una cola de llamadas existente que ya haya configurado.  Otro **operador automático**: puede usar un operador automático existente para crear un segundo nivel de opciones de menú que contenga un submenú. Estos operadores automáticos se conocen como operadores automáticos anidados. **Reproducir el texto de las opciones de menú**: puede usar esta opción para configurar el mensaje que quiera que se reproduzca. |
|**3**|**Texto del menú**: para crear un mensaje para el menú principal puede usar la característica Texto a voz o cargar un archivo de audio (.wav, .mp3 o .wma). Puede escribir el mensaje en el cuadro **Las personas que llaman escucharán** o grabar un archivo de audio y decir, por ejemplo: "Pulse o diga 1 para Ventas. Pulse o diga 2 para Servicios. Pulse o diga 3 para Atención al cliente. Para hablar con el operador, pulse o diga 0. Para escuchar este mensaje de nuevo, pulse la tecla de asterisco o diga Repetir". **Crear un mensaje de asistencia por voz personalizado**: si elige esta opción, debe introducir el texto que desea que lea el sistema (hasta 1000 caracteres). **Cargar un archivo de audio**: si elige esta opción, deberá grabar el saludo y cargar el archivo de audio (en formato .wav, .mp3 o .wma). |
|**4**|**Marcado por nombre** Si elige esta opción, se permitirá la personas que llaman para buscar personas en su organización mediante la búsqueda en el directorio. Puede seleccionar las personas que se mostrarán como disponible o no está disponible para acceso telefónico por nombre mediante la configuración de estas opciones en la página de **ámbito de marcado**. Cualquier usuario en línea con una licencia de **Sistema telefónico** o todos los usuarios alojados en local usando Skype empresarial Server 2015 o Lync Server 2013, puede encontrarse con acceso telefónico por su nombre.> [!CAUTION]> Los usuarios alojados en local con Lync 2010 **no se puede llegar** con acceso telefónico por su nombre.          |
|**5**|**Editar las opciones de menú** Opciones de menú se pueden agregar o eliminar mediante los botones de clave en el teclado. Para agregar una opción de menú, presione la tecla correspondiente en el teclado. Las teclas en uso cambiará de color y aparece debajo de la fila correspondiente de opciones. Para eliminar una opción de menú, simplemente haga clic en la clave correspondiente en el control de teclado para anular la selección de esta clave. Se quitará la fila de asignación de clave.> [!TIP]> Debe actualizar el texto del menú indicaciones o volver a grabar el audio por separado al agregar a quitar opciones porque no hacerse automáticamente para el aviso de menú existente.           Puede agregar y quitar en cualquier orden cualquier opción de menú y las asignaciones de teclas no tienen que estar continuo. Es posible, por ejemplo, para crear un menú con claves 0, 1 y 3 asignado a opciones, aunque no se usa la clave 2.> [!NOTE]> Las teclas * (repetir) y # (atrás) reservados por el sistema y no se pueden reasignar. Si se habilita el reconocimiento de voz, presione * se corresponden con "Repetir" y # se corresponden con los comandos de voz "Atrás".           |
|| Para configurar sus opciones de menú, después de seleccionar la(s) teclas(s), deberá: **Escriba el nombre de la opción** Esto puede tener hasta 64 caracteres y puede contener varias palabras como "Servicio al cliente" o "operaciones y motivos". Si se habilita el reconocimiento de voz, reconocerá automáticamente el nombre y la persona que llama podrán presione 3, diga "tres" o diga "Servicio al cliente" para seleccionar la opción asignada a la clave 3. El siguiente paso consiste en seleccionar dónde debe enviarse la llamada si se pulsa la tecla correspondiente o si se selecciona la opción mediante reconocimiento de voz. La llamada puede enviarse a: **Operador** Si ya está configurado el operador, se asigna automáticamente a clave 0, pero también puede eliminar o reasignar a otra clave. Si el operador no está configurado para cualquier tecla, el comando de voz "Operador" se deshabilitará demasiado. Una **persona de la empresa** con una licencia de **Sistema telefónico** que está habilitada para telefonía IP empresarial o asignada a un Plan de llamada en Office 365. Puede configurarlo para que la persona que llama se pueden enviar al correo de voz. Para ello, seleccione la **persona de su empresa** y establezca esta persona a sus llamadas reenvía directamente al correo de voz.> [!NOTE]> **Persona de su empresa** puede ser un usuario en línea o un usuario hospedado en local con Skype para empresarial Server 2015 o Lync Server 2013. Lync Server 2010 no es compatible.          **Cola de llamadas** Con una opción de cola de llamada permite la llamada se transfiera a una cola de llamada existente que ha configurado. Un **operador automático**: puede usar un operador automático existente para crear un segundo nivel de opciones de menú que contenga un submenú. Estos operadores automáticos se conocen como operadores automáticos anidados. > [!NOTE]>  Las **horas de trabajo** de los operadores automáticos de anidados (o de segundo nivel) también se utilizará, incluido para las llamadas que se envía desde otros operadores automáticos que se han configurado.          |
   
### Seleccione página de días festivos (disponible para los clientes de vista previa)

Puede agregar hasta 20 días festivos programadas para cada operador automático.
  
![Setting up Holidays in auto attendant](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
|||
|:-----|:-----|
|**1**|**Agregue un día festivo** Escriba un nombre para el nuevo día festivo en el campo **nombre de vacaciones**.Nombres de vacaciones pueden constar de un máximo de 64 caracteres y deben ser únicos para el mismo operador automático. Por ejemplo, no puede tener dos días festivos denominadas "Acción de gracias" en el mismo operador automático.|
|**2**|**Saludo de vacaciones** El saludo de vacaciones es opcional y puede establecer en **ninguna**. En este caso, el llamador no escuchará ningún mensaje o saludo antes de la llamada se controla mediante una de las opciones que seleccione. También puede cargar un archivo de audio (en formatos WAV, mp3 o .wma) o crear un saludo personalizado mediante la característica texto a voz. **Ninguno** Saludo no se reproducirá cuando personas llaman al número de teléfono de operador automático. **Crear un personalizado de saludo** Si elige esta opción, escriba el texto que desea que el sistema lea (hasta 1000 caracteres). ¡Por ejemplo, puede escribir "feliz año nuevo! Nuestras oficinas están actualmente cerrados."en el cuadro **escucharán las personas que llaman**. **Cargar un archivo de audio** Si selecciona esta opción, grabar el saludo de vacaciones y, a continuación, cargue el archivo de audio (en un formato .wav,. mp3 o .wma).|
|**3**|**¿Qué sucede con las llamadas después el saludo?** Puede seleccionar qué ocurre con las llamadas que llegan durante este vacaciones. Puede elegir entre las siguientes opciones: **Desconectar** La persona que llama se desconectarán tras escuchar el saludo de vacaciones. **Redirigir llamada**: puede usar esta opción para enviar la llamada automáticamente a:  Una **persona de la empresa** con una licencia de **Sistema telefónico** que está habilitada para telefonía IP empresarial o asignada llamar a los planes de Office 365. Puede configurarlo para que la persona que llama se pueden enviar al correo de voz. Para ello, seleccione la **persona de su empresa** y establecer esta persona a sus llamadas reenvía directamente al correo de voz.> [!NOTE]> **Persona de su empresa** puede ser un usuario en línea o un usuario hospedado en local con Skype para empresarial Server 2015 o Lync Server 2013. Lync Server 2010 no es compatible.           Una **Cola de llamadas** para transferir la llamada a una cola de llamadas existente que ha configurado Otro **operador automático**, para crear un segundo nivel de opciones de menú que contiene un submenú. Se denominan a operadores automáticos anidada. > [!NOTE]>  De forma predeterminada, todas las llamadas que llegan durante un período de vacaciones se establecen en Desconectar después el saludo (si existe), por lo que debe especificar una redirección si se desea un comportamiento diferente.          |
|**4**|**Cuando quiera las vacaciones para iniciar y terminar?** Especifique la fecha de inicio de vacaciones en formato mm/dd/aaaa y, a continuación, seleccione una hora de inicio, la fecha de finalización y la hora de finalización, cuando se le solicite en la tabla de intervalo de fechas.Puede especificar hasta 10 diferentes rangos de fecha para un día festivo. Por ejemplo, puede agregar intervalos de fechas para las vacaciones de fin de año de hasta 10 años. Un día festivo puede abarcar varios días.Para agregar nuevas vacaciones fecha rangos (por ejemplo, para el próximo año), haga clic en **Agregar otra** y, a continuación, escriba un nuevo conjunto de fechas de inicio y finalización de las vacaciones.Días festivos anidadas también son compatibles. Por ejemplo, puede anidar varios días festivos dentro de un período de tiempo de "salto de vacaciones": **· 24 de diciembre a través 3 de enero:** "Feliz Navidad Nuestras oficinas actualmente están cerrados. Nos se vuelva a abrir el 4 de enero." **· 25 de diciembre:** "Feliz Navidad! Nuestras oficinas actualmente están cerrados. Nos se vuelva a abrir el 4 de enero." **· 1 de enero:** "feliz año nuevo! Nuestras oficinas actualmente están cerrados. Nos se vuelva a abrir el 4 de enero."|
   
Después de guardar al operador automático, los días festivos aparecen en la pestaña de **vacaciones**, donde puede editar, agregar o modificar la configuración de vacaciones.
  
### Página Seleccionar ámbito de marcado

En esta página, puede configurar qué usuarios de su organización estará enumerados en su directorio y está disponible para acceso telefónico por nombre cuando una persona que llama a su organización.
  
![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
|||
|:-----|:-----|
|**1** <br/> | La opción **Incluir** ofrece dos posibilidades: <br/> **Online todos los usuarios** Uso de esta opción permite todas las personas de su organización que desea incluir en la búsqueda en el directorio. Todos los usuarios en línea con una licencia de **Sistema telefónico**, así como los usuarios alojados en local usando Skype empresarial Server 2015 o Lync Server 2013 que tienen llamar a los planes de Office 365, se mostrarán.  <br/> **Personalizado** Si usa esta opción, puede buscar un grupo de Office 365, lista de distribución o grupo de seguridad que ha creado en su organización y las personas que agregan a este grupo de Office 365, lista de distribución o grupo de seguridad que están en **usuarios en línea con un Licencia de sistema de teléfono** u hospedado en local con Skype para empresarial Server 2015 o Lync Server 2013. Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad. <br/> > [!CAUTION]>  Los usuarios locales de implementaciones de Lync Server 2010 no aparecerá cuando alguien busca en el directorio mediante acceso telefónico por su nombre.          |
|**2** <br/> | La opción **Excluir** ofrece dos posibilidades: <br/> **Ninguno**: esta opción indica que no se debe excluir a ningún usuario de la búsqueda en directorios.  <br/> **Personalizado** Si usa esta opción, puede buscar un grupo de Office 365, lista de distribución o grupo de seguridad que ha creado en su organización, y todas las personas que se agregan a este grupo de Office 365, lista de distribución o grupos de seguridad se pueden excluir de la búsqueda en el directorio. Puede agregar varios grupos de Office 365, listas de distribución y grupos de seguridad. <br/> > [!CAUTION]>  Los usuarios locales de implementaciones de Lync Server 2010 no aparecerá cuando alguien busca en el directorio mediante acceso telefónico por su nombre.          |
   
> [!NOTE]
> Puede tardar hasta 36 horas para que su nombre aparece en el directorio cuando alguien utiliza marcado por nombre con el reconocimiento de voz de un usuario nuevo. 
  
Después de escribir todos los campos obligatorios y configurar el control de los menús y opciones de llamada, haga clic en **Guardar**.
  
## Edición y la prueba de operadores automáticos

Una vez que haya guardado al operador automático, se mostrará en la página de **operadores automáticos**. Esto le permitirá ver rápidamente algunas de las opciones que ha configurado, incluido el nombre, el número de teléfono, el idioma y el estado.
  
Si desea realizar cambios en un operador automático, seleccione al operador automático y, a continuación, en el panel Acción, haga clic en **Editar**.
  
Rápidamente puede realizar una llamada de prueba a su operador automático mediante el botón **probar** en el panel acción.
  
## ¿Desea obtener más información?

También puede usar Windows PowerShell para crear y configurar operadores automáticos.
  
### Cmdlets para operadores automáticos

Estos son los cmdlets que necesita para administrar un operador automático.
  
||||
|:-----|:-----|:-----|
|[New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796493.aspx) <br/> |[Get-CsOrganizationalAutoAttendantSupportedTimeZone]( https://technet.microsoft.com/en-us/library/mt796483.aspx) <br/> |[New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/en-us/library/mt796488.aspx ) <br/> |
|[Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796486.aspx) <br/> |[Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/en-us/library/mt796481.aspx) <br/> |[New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/en-us/library/mt796489.aspx) <br/> |
|[Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796482.aspx ) <br/> |[New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/en-us/library/mt796480.aspx) <br/> |[New-CsOnlineTimeRange](https://technet.microsoft.com/en-us/library/mt796491.aspx ) <br/> |
|[Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796492.aspx) <br/> |[New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/en-us/library/mt796484.aspx ) <br/> |[New-CsOnlineSchedule](https://technet.microsoft.com/en-us/library/mt796490.aspx) <br/> |
|[New- CsOnlineAudioFile](https://technet.microsoft.com/en-us/library/mt796479.aspx) <br/> |[New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/en-us/library/mt796485.aspx ) <br/> |[New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/en-us/library/mt796487.aspx ) <br/> |
|[Exportar-CsOrganizationalAutoAttendantHolidays (solo para clientes de vista previa)](https://docs.microsoft.com/en-us/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) <br/> |[Get-CsOrganizationalAutoAttendantHolidays (solo para clientes de vista previa)](https://docs.microsoft.com/en-us/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps) <br/> |[Importar-CsOrganizationalAutoAttendantHolidays (solo para clientes de vista previa)](https://docs.microsoft.com/en-us/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) <br/> |
|[Nuevo-CsOnlineDateTimeRange (solo para clientes de vista previa)](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) <br/> |||
   
### Más información sobre Windows PowerShell

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

