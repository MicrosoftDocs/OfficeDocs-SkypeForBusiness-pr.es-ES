---
title: "Crear una cola de llamada del sistema telefónico"
ms.author: tonysmit
author: tonysmit
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061

description: "Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. "
---

# Crear una cola de llamada del sistema telefónico

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](67ccda94-1210-43fb-a25b-7b9785f8a061.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/67ccda94-1210-43fb-a25b-7b9785f8a061). 
  
Llamada de sistema colas incluyen saludos que se usan cuando alguien llama a un número de teléfono de su organización, la capacidad de poner automáticamente las llamadas en espera y la capacidad de buscar para el siguiente agente de llamada disponibles controlar la llamada cuando las personas que llamada escuchan música en espera. Puede crear uno o varios colas de llamada para su organización.
  
Pueden proporcionar colas de llamada del sistema de teléfono:
  
- Un mensaje de saludo empresarial.
    
- Música que se reproduce mientras los usuarios se mantienen a la espera.
    
- Desvío de llamadas para llamar a los agentes en las listas de distribución de correo y grupos de seguridad.
    
- Realizar la configuración de tamaño máximo de cola de llamada, tiempo de espera y opciones de control de llamada.
    
Cuando alguien llama a un número de teléfono que se establece el arriba con una cola de la llamada, escuchará un saludo primero (si se configura cualquiera) y, a continuación, se coloca en la cola y espere a que el siguiente agente de llamada disponibles. La persona que llama escuchará música mientras se encuentran en espera en espera y, a continuación, se ofrecen las llamadas a los agentes de llamada de la forma  *Primero en ENTRAR, primero en salir*  (FIFO).
  
Todas las llamadas en espera en la cola se se distribuye con un operador enrutamiento modo o serie enrutamiento (disponible para los clientes de vista previa):
  
- Con el enrutamiento de operador, la primera llamada en la cola desvían a todos los agentes al mismo tiempo.
    
- Con el enrutamiento de serie, la primera llamada en la cola desvían a todos los agentes de llamada uno por uno (disponible para los clientes de vista previa).
    
-     > [!NOTE]
    > No se llamará agentes de llamada **sin conexión**, han establecido su presencia en **No molestar,** o han optado fuera de la cola de la llamada.
  
- Solo se enviará a los agentes de llamadas una notificación de llamada entrante cada vez (la de la llamada que se encuentra en primer lugar de la cola).
    
- Después de que un agente de llamadas acepte la llamada, la siguiente llamada entrante de la cola se enviará a los demás agentes de llamadas.
    
## Paso 1: tareas iniciales

Para comenzar a utilizar colas de llamadas, es importante recordar algunas cosas:
  
- Licencia Enterprise E5 o una licencia Enterprise E3 plus **Sistema telefónico**, debe tener su organización (como mínimo). El número de licencias de usuario de **Sistema de teléfono** asignados afecta a la cantidad de números de servicio que están disponibles para utilizarse para colas de llamada. El número de colas de llamada que puede tener depende del número de licencias de **Sistema telefónico** y **Conferencias de Audio** que se asignan en su organización. Para obtener más información sobre licencias, vaya[Skype para Business y Microsoft Teams licencias de complemento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Para desviar llamadas a las personas de su organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitadas para telefonía IP empresarial o tiene Office 365 llamar a los planes. Vea[Asignar Skype para Business y Microsoft Teams licencias](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Para habilitarlos para telefonía IP empresarial, puede usar Windows PowerShell. Ejecutar por ejemplo:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obtener más información sobre planes una llamada de Office 365, consulte [¿Qué planes de llamada en Office 365?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) y[Llamar a los planes para Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).
    
    > [!NOTE]
    > Los usuarios alojados en local con Lync Server 2010 no se admiten como un agentes de cola de llamadas. 
  
- Solo puede asignar y de pago y números de teléfono de un servicio gratuito que obtuvo en el **Skype centro de administración de la empresa** o transferido desde otro proveedor de servicios a colas de llamada de sistema telefónico. Para obtener y utilizar números gratuitos de servicio, debe configurar créditos de comunicaciones.
    
    > [!NOTE]
    > Los números de teléfono de usuario (suscriptor) no se pueden asignar a las colas de llamadas; solo se pueden usar números de teléfono de servicio de pago y gratuitos. 
  
- Cuando se distribuye las llamadas entrantes de una cola de llamada de sistema telefónico, estos clientes son compatibles para los agentes de llamada:
    
  - Cliente de escritorio de Skype Empresarial 2016 (versiones de 32 y 64 bits)
    
  - Cliente de escritorio de Lync 2013 (versiones de 32 y 64 bits)
    
  - Todos los modelos de teléfonos IP admitidos para Skype Empresarial Online. Consulte [Obtener teléfonos con Skype Empresarial Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Mac Skype empresarial Client (versión 16.8.196 y posteriores)
    
  - Android Skype empresarial Client (versión 6.16.0.9 y posteriores)
    
  - iPhone Skype empresarial Client (versión 6.16.0 y posteriores)
    
  - iPad Skype empresarial Client (versión 6.16.0 y posteriores)
    
## Paso 2: obtener o transferir números de servicio de pago o gratuitos

Para poder crear y configurar las colas de llamada, necesitará obtener o transferir su pago existente o un servicio gratuito números. Después de obtener el pago o números de teléfono gratuitos de servicio, aparecerá en **Skype centro de administración de negocio** > **voz** > **números de teléfono** y a continuación, usará **tipo número** en la lista figurar como **servicio gratuito**. Para obtener los números de servicio, vea [Obtener números de teléfono de servicio de Skype Empresarial](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) o si desea transferir y el número de servicio existente, consulte[Números de teléfono de transferencia a Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si está fuera de los Estados Unidos, no puede usar la Skype centro de administración de la empresa para obtener números de servicio. Vaya [Administrar los números de teléfono de su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo desde fuera de Estados Unidos.
  
## Paso 3: crear una cola de llamadas nueva

En el **Centro de administración de Skype Empresarial**, haga clic en **Enrutamiento de llamadas** > **Colas de llamadas**, y después en **Agregar nueva**:
  
### Definir el nombre para mostrar de la cola de llamadas, el número de teléfono y el dominio (si disponible)

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Nombre**: introduzca un nombre para mostrar descriptivo para la cola de llamadas. Este campo es obligatorio y puede tener hasta 64 caracteres, espacios incluidos.  <br/> Este nombre se mostrará en la notificación de la llamada entrante.  <br/> |
|**2** <br/> |**Número de teléfono** Seleccione un pago de servicio o el número de teléfono gratuito para la cola de llamada. Esto es opcional. <br/> Si no se enumera ninguno, deberá obtener los números de servicio para poder crear esta cola de llamadas. Para obtener los números de servicio, consulte [Obtener números de teléfono de servicio de Skype Empresarial](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) <br/> |
|**3** <br/> |**Dominio**: si está disponible, elija el dominio de Office 365 que desee usar. Esta opción solo está disponible si tiene más de un dominio en uso con Office 365. Si tiene más de uno, deberá elegir un nombre de dominio de la lista.  <br/> Por ejemplo, puede tener un dominio como:  _contoso.com or redmond.contoso.com_.  <br/> |
   
### Establecer el mensaje de saludo y la música que se debe reproducir durante el tiempo en espera

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Saludo** es opcional. Este es el saludo que se reproduce para las personas que llaman al número de llamada de cola. <br/> Puede cargar un archivo de sonido (.wav,. mp3 o .wma formatos).  <br/> |
|**2** <br/> |**Música en espera** Puede usar el valor predeterminado de música en espera proporcionado con la cola de llamada o puede cargar un archivo de audio en formatos WAV, mp3 o .wma para utilizarlo como su personalizado música en espera. <br/> |
   
### Seleccione el método de distribución de llamada (disponible para los clientes de vista previa)

![Shows the call distribution method options](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Llame al método de distribución.** Puede elegir el **operador** o **serie** para el método de distribución de cola de llamada. Todas las colas de llamada nuevos y existentes tendrá enrutamiento operador seleccionado de manera predeterminada. Para usar la redirección de serie, explícitamente debe elegir la opción de distribución de **serie** en la interfaz de usuario y los cmdlets. <br/> Cuando se elige el enrutamiento de la serie y se guarda la cola de la llamada, el de la cola recibirá las llamadas a los agentes uno por uno, empezando desde el principio de la lista de agentes. Si un agente descarta o no reanudar una llamada, la llamada desvían al agente siguiente en la lista e intentará todos los agentes de uno en uno hasta que se ha seleccionado o tiempos de espera en la cola.  <br/> > [!NOTE]> Enrutamiento de serie omitirá a agentes con **sin conexión**, han establecido su presencia en **No molestar** u **dejado de participar** de obtención de llamadas de esta cola.          |
   
### Seleccione un agente de cambiar de opinión opción (disponible para los clientes de vista previa)

![Shows the agent opt out check box](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Agente de cambiar de opinión opción** Puede elegir permitir que los agentes de cola de llamada para no participar en realizando llamadas de una cola determinada seleccionando el **Agente de cambiar de opinión opción**.  <br/> Activar esta opción permite que todos los agentes de esta cola para iniciar o detener la recepción de llamada desde esta cola de llamada en le. Puede revocar los privilegios de rechazar agente en cualquier momento, desactive la casilla de verificación causando agentes de convertirse en elegido automáticamente en para volver a esta cola (el valor predeterminado para todos los agentes).  <br/> Para obtener acceso a la opción de anulación, agentes pueden hacer lo siguiente:  <br/> 1. Abra **Opciones** de su escritorio Skype empresarial Client. <br/> 2. en la ficha **Desvío de llamadas**, haga clic en el vínculo **Editar configuración en línea** <br/> 3. en la página de configuración de usuario, haga clic en **Llamar colas** y, a continuación, desactive las casillas de las colas para las que desean cambiar de opinión. <br/> |
   
### Agregar agentes de llamadas a una cola de llamadas

![Set up call queues.](../images/9c0c551b-218b-4268-9b73-c85000c99296.png)
  
|||
|:-----|:-----|
|**1** <br/> | Agentes de llamadas (50 como máximo) pueden ser: <br/>  Un usuario en línea con una licencia de **Sistema telefónico** habilitada para telefonía IP empresarial o con un Plan de llamada. <br/> > [!NOTE]>  Para desviar llamadas a las personas de su organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitadas para telefonía IP empresarial o tiene un Plan de llamada. Vea[Asignar Skype para Business y Microsoft Teams licencias](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Para habilitarlos para telefonía IP empresarial, puede usar Windows PowerShell. Ejecutar por ejemplo:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`           Usuarios en línea con una con una licencia de **Sistema telefónico** o una llamada Plan que se agregan a una lista de distribución o grupo de seguridad habilitados para correo. Puede tardar hasta 30 minutos para un nuevo agente de agregado de una lista de distribución o un grupo de seguridad para empezar a recibir llamadas de una cola de la llamada. Un grupo de seguridad o lista de distribución recién creado puede tardar hasta 48 horas esté disponible para su uso con colas de llamada. <br/> > [!NOTE]>  Office 365 (grupos moderna) no se pueden usar con colas de llamada.          > [!NOTE]>  Los usuarios alojados en local con Lync Server 2010 no se admiten.          |
   
### Establecer el tamaño máximo de cola y el tiempo de espera máximo

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
|||
|:-----|:-----|
|**1**|**Máximo llamadas en la cola** Use esta opción para configurar las llamadas máximas que pueden esperar en la cola al mismo tiempo. El valor predeterminado es 50, pero puede ser de 0 a 200.Una vez alcanzado el límite, la llamada se administrará del modo que establezca en el ajuste **Cuando se alcanza el número máximo de llamadas**, que se describe a continuación.|
|**2**|**Cuando se alcance el número máximo de llamadas** Cuando la cola de llamada llega a su tamaño máximo (establecida mediante la configuración de **máxima llamadas en la cola** ), puede elegir qué ocurre con las llamadas entrantes nuevas. **Desconectar con una señal de línea ocupada**: se desconectará la llamada. **Desviar esta llamada** Cuando selecciona esta opción, tendrá estas opciones: **Persona de la empresa** Un usuario en línea con una licencia de **Sistema telefónico** y estar habilitada para telefonía IP empresarial o tiene un Plan de llamada. Puede configurarlo para que la persona que llama se pueden enviar al correo de voz. Para ello, seleccione una **persona de su empresa** y establezca esta persona a sus llamadas reenvía directamente al correo de voz.> [!NOTE]>  Los usuarios alojados en local con Lync Server 2010 no se admiten.          **Cola de llamadas** Debe ya ha creado otra cola de llamada, pero después, puede seleccionar esa cola de llamada. **Operador automático** Debe ya ha creado a un operador automático, pero después, puede seleccionar el operador automático. Consulte[Configurar un operador automático de sistema telefónico](set-up-a-phone-system-auto-attendant.md). |
|**3**|**Cuánto tiempo puede esperar una llamada en la cola**: también puede decidir cuánto tiempo puede ponerse en espera una llamada en la cola antes de redirigirla o desconectarla. Adónde se redirigirá depende de cómo configure el ajuste **Cuando una llamada agota el tiempo de espera**. Puede establecer un intervalo de entre 0 y 45 minutos.> [!NOTE]> **Disponible para los clientes de vista previa:** El valor de tiempo de espera se puede establecer en segundos, en intervalos de 15 segundos. Esto le permite manipular el flujo de llamadas con mayor detalle. Por ejemplo, puede especificar que todas las llamadas que no responde un agente 30 segundos después vayan a un operador automático de búsqueda de directorio.          |
|**4**|**Cuando una llamada agota el tiempo de espera**: puede elegir lo que sucede con las llamadas cuando alcanzan el límite establecido en el ajuste **Cuánto tiempo puede esperar una llamada en la cola**: **Desconectar**: la llamada se desconectará. **Desviar esta llamada** Cuando selecciona esta opción, tendrá estas opciones: **Persona de la empresa** Un usuario en línea con una licencia de **Sistema telefónico** y estar habilitada para telefonía IP empresarial o tiene llamar a los planes. Puede configurarlo para que la persona que llama se pueden enviar al correo de voz. Para ello, seleccione una **persona de su empresa** y establezca esta persona a sus llamadas reenvía directamente al correo de voz.> [!NOTE]>  Los usuarios alojados en local con Lync Server 2010 no se admiten.          **Cola de llamadas** Debe ya ha creado otra cola de llamada, pero después, puede seleccionar esa cola de llamada. **Operador automático** Debe ya ha creado a un operador automático, pero después, puede seleccionar el operador automático. Consulte[Configurar un operador automático de sistema telefónico](set-up-a-phone-system-auto-attendant.md). |
   
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
  
## ¿Desea obtener más información?

También puede usar Windows PowerShell para crear y configurar colas de llamadas.
  
### Cmdlets de colas de llamadas

Estos son los cmdlets que necesita para administrar una cola de llamadas.
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
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
  

