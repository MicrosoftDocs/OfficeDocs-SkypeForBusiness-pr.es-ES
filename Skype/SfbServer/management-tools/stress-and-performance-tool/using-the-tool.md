---
title: Uso de la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: Para ejecutar la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento, aquí necesite que puedan administrar usuarios, contactos y perfiles de usuario, configurar la herramienta para la ejecución y, a continuación, revise los resultados o los resultados producidos por la herramienta.
ms.openlocfilehash: 7ce25ec13af020734e0784392e457f96399a2398
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884845"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Uso de la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento
 
Para ejecutar la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento, aquí necesite que puedan administrar usuarios, contactos y perfiles de usuario, configurar la herramienta para la ejecución y, a continuación, revise los resultados o los resultados producidos por la herramienta.
  
Hay cuatro áreas relacionadas con la que se ejecuta el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento (el archivo ejecutable es LyncPerfTool.exe):
  
- [Crear usuarios y contactos](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurar perfiles de usuario](using-the-tool.md#BKMK_UserProfile)
    
- [Ejecute LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpretar los resultados](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Crear usuarios y contactos
<a name="BKMK_CreateUsersAndContacts"> </a>

Debe usar la Skype para la herramienta de aprovisionamiento de usuario Business Server 2015 (2015 de byte único) (UserProvisioningTool.exe) para crear usuarios y contactos de su esfuerzo y las pruebas de rendimiento.
  
Ésta es una lista de términos útiles que pueden ser útiles al leer a través de los temas:
  
- **Unidad organizativa** - unidad organizativa de los servicios de dominio de Active Directory (AD DS) activo (OU).
    
- **Federados / entre el grupo de servidores** - los usuarios que pueden comunicarse con usuarios de otros servicios de mensajería instantánea (mi).
    
- **Las listas de distribución** - o listas de distribución. Estos son objetos en AD DS que contenga una lista de usuarios de AD DS. Los utilizan para facilitar la comunicación entre los grupos de personas.
    
- **Servicio de información de ubicación** : Skype el servicio de Business Server 2015 que, cuando ha habilitado y configurado por teléfono, permite la recuperación de ubicación física para los servicios Enhanced 911 (E911).
    
- **Los números de teléfono de Estados Unidos** , los números de teléfono asignados al usuario además el URI del SIP que se usa para enrutar las llamadas entrantes y salientes en búsqueda de número inversa (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Crear usuarios y contactos mediante el uso de UserProvisioningTool.exe

> [!NOTE]
> Antes de comenzar, asegúrese de absolutamente que ha iniciado sesión como miembro del grupo de seguridad Administradores de dominio para ejecutar esta herramienta. Debe hacer esto, debido a que se va a crear usuarios de Active Directory. 
  
Se debe usar la Skype para la herramienta de aprovisionamiento de usuario empresarial Server para crear usuarios y contactos de simulación de carga.
  
El **Skype para la herramienta de aprovisionamiento de usuario Business Server** se instala con el paquete de **Skype para Business Server Stress and Performance Tool** . Asegúrese de que se ha ejecutado el instalador del paquete (CapacityPlanningTool.msi) en el servidor Front-End o el servidor Standard Edition que desea probar.
  
Puede iniciar el Skype para la herramienta de aprovisionamiento de usuario empresarial Server ejecutando el archivo UserProvisioningTool.exe (que se encuentra en % InstalledDirectory%LyncStressAndPerfTool\LyncStress) en el servidor Front-End o en el servidor Standard Edition.
  
> [!IMPORTANT]
> Cuando se crea un gran número de usuarios (por ejemplo, 10.000 o más), ejecute el UserProvisioningTool.exe. Debe hacerlo porque la herramienta se puede crear y configurar usuarios *nuevo* AD.
  
Cuando se abre la herramienta de aprovisionamiento de usuario, haga clic en configuración y seleccione la configuración de carga. 
  
Para empezar a configurar los usuarios y contactos, cargar el archivo predeterminado incluido con el paquete, llamado "SampleData.xml". Esto va a rellenar automáticamente los campos con datos de ejemplo que necesita cambiar para que sea relevante para la implementación.
  
Si tiene un archivo XML preconfigurado que ya contiene la configuración personalizada, se puede cargar ese archivo en su lugar. Rellene los campos en la herramienta de aprovisionamiento de usuario, tal como se describe en las secciones siguientes.
  
### <a name="to-configure-server-options"></a>Para configurar las opciones de servidor:

1. En el campo **FQDN de grupo de servidores Front-End** , escriba el nombre de dominio completo (FQDN) del servidor Standard Edition o el grupo de servidores Front-End donde desea hospedar los usuarios.
    
2. En el campo **Prefijo de nombre de usuario** , escriba el prefijo que se desea usar para bust los nombres de usuario para realizar pruebas (por ejemplo, "usuario de prueba").
    
3. En el campo **contraseña** , escriba una contraseña que se va a usar en todas las cuentas de usuario de prueba.
    
4. En el campo de la **Cuenta de dominio** , escriba el nombre de dominio de su dominio de Active Directory actual (el uno en el que desea crear los usuarios de prueba).
    
5. En el campo **Unidad organizativa** , escriba el nombre de dominio de Active Directory donde desea crear estos usuarios de prueba. (Si ya no existe la unidad organizativa, éste podrá ser creado).
    
6. En el campo **código de área de teléfono** , escriba el código de área de tres dígitos que se usará en todas las cuentas de usuario de prueba. Asegúrese de que el código de área elegida no entre en conflicto con los códigos de área de los demás usuarios en AD.
    
7. Haga clic para seleccionar la casilla de verificación **Habilitado para voz** , si desea habilitar a los usuarios de prueba para Enterprise Voice.
    
8. En el campo **Número de usuarios** , asigne el número total de usuarios de prueba que desea crear.
    
9. En el campo **Índice iniciar** , asigne el número inicial que se van a utilizar como un sufijo para el prefijo de nombre de usuario (por ejemplo, el prefijo es "Usuario de prueba" y finalizará el primer nombre en "0" en el ejemplo siguiente).
    
     ![Herramienta de aprovisionamiento de usuarios donde se muestra la ficha Creación de usuario.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Crear el botón de los usuarios

Al hacer clic en el botón **Crear usuarios** , se validan los parámetros de entrada que ha especificado. Si hay errores de validación, se le pedirá a corregirlos. O bien, si todos los valores son correctos, los usuarios se iniciarán aparezca en AD (en cualquier unidad organizativa que especificó). Verá una barra de progreso en la parte inferior de la herramienta se ejecuta. No cierre la aplicación mientras está activa la barra de progreso.
  
Creación de usuario tarda, así pues, el plan de según corresponda. Este proceso puede tardar desde varios minutos para unos pocos usuarios, unas cuantas horas para un gran número de usuarios.
  
Si no tiene acceso al controlador de dominio de Active Directory en su entorno de prueba, todavía puede validar la creación del usuario al iniciar sesión como uno de los usuarios en el intervalo de usuarios especificado para crear. Recuerde que debe usar el prefijo y el sufijo, junto con el @sipDomain como el nombre de usuario. Este es un ejemplo: <em>TestUser20@contoso.net</em> .
  
> [!NOTE]
> Si los usuarios ya existen, al hacer clic en el botón Crear usuarios actualizará con los cambios de configuración. 
  
#### <a name="delete-users-button"></a>Eliminar botón usuarios

Al hacer clic en el botón **Eliminar usuarios** , se validará los parámetros de entrada de la ficha. Si hay errores de validación, se le pedirá corregirlos, y si los valores de entrada son correctos, los usuarios de prueba especificado se deshabilita y se eliminará de Active Directory. Una vez más, aparecerá una barra de progreso en la parte inferior de esta ficha y no debe cerrar la aplicación mientras está activa la barra de progreso.
  
> [!NOTE]
> Se admiten sólo los números de teléfono con formato de Estados Unidos. Los números de teléfono siempre se asignan a los usuarios y todos los usuarios creados por UserProvisioningTool.exe están habilitados para Enterprise Voice de forma predeterminada. Los escenarios que usan el número de teléfono, como operador automático de conferencia o llamadas de UC-RTC, use este número de teléfono para enrutar las llamadas correctamente. Por este motivo, *cada usuario* debe tener un *número de teléfono único* .
  
> [!NOTE]
> **Si tiene que crear dos veces a los usuarios, se producirá un error en el comando a menos que utilice un código de área diferente, o si se han deshabilitado los usuarios anteriores mediante el cmdlet Disable-CsUser.**
  
> [!IMPORTANT]
> Antes de crear contactos, primero debe completar la replicación de usuarios (que se realiza desde la ficha de los usuarios). 
  
> [!IMPORTANT]
> Si se acaba de crear los usuarios, debe esperar hasta que Skype para la replicación del servidor empresarial completa y rellena las cuentas de usuario en la base de datos. **Si los usuarios no ha terminado de replicar, verá un error.** Sabrá cuando los usuarios hayan terminado de replicar si se ha iniciado la Skype para el servicio Front-End de Business Server 2015, o mediante la ejecución del cmdlet Get-CsUser de correctamente en el último usuario del número total especificado.
  
#### <a name="contacts-creation-tab"></a>Ficha de creación de contactos

Esta ficha permite proporcionar detalles de los contactos de los usuarios para las pruebas.
  
![Herramienta Aprovisionamiento de usuarios donde se muestra la pestaña Creación de contenido.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Para configurar los contactos de los usuarios, haga lo siguiente:

1. En el campo **Contactos promedio por usuario** , escriba el número promedio de contactos para rellenar en las listas de contactos para cada usuario.
    
2. Seleccione la casilla de verificación **fijo** si desea crear un número igual de contactos para todos los usuarios. Si desea variar el número de contactos creados para los usuarios, desactive dicha casilla de verificación.
    
3. En el campo **Promedio grupos de contactos por usuario** , escriba el número de grupos de contactos por usuario. Este número debe ser menor que el **Promedio de contactos por usuario**.
    
4. En el campo **federados / cruce el porcentaje de los contactos del grupo de servidores** , asigne un número entre 0 y 100. Este porcentaje de contactos se creará con los usuarios federados.
    
5. En el campo **federados / cruce prefijo de usuario del grupo de servidores** , asigne el nombre de usuario para los usuarios federados que se agregará a las listas de contactos de los usuarios locales.
    
6. En el campo **federados / cruce el dominio SIP de usuario de grupo de servidores** , asigne el nombre de dominio SIP de los usuarios federados.
    
7. En la ficha de **Creación de usuario** Asegúrese de que la información es correcta. Los contactos se crearán de valores en la ficha de creación de usuario.
    
8. Haga clic en **Crear contactos** para comenzar la creación de contactos. Este proceso puede tardar varios minutos. Una vez completada, aparecerá un cuadro de diálogo con el mensaje "operación se realizó correctamente." Puede validar los contactos a los que se crearon mediante inicio de sesión como un usuario que se creó desde la ficha de creación de usuario.
    
> [!NOTE]
> Después de crean los contactos, esta herramienta reiniciará todos los servidores Front-End del grupo de servidores de destino. Puede tardar más tiempo (hasta 2 horas) para los servidores Front-End iniciar, según la cantidad de contactos se crearon por esta operación. 
  
#### <a name="distribution-list"></a>Lista de distribución

El Skype para Business Server 2015 herramienta de esfuerzo y rendimiento puede simular la característica de expansión de lista de distribución (DL) de la Skype para cliente empresarial 2015. Puede omitir este paso si no desea habilitar la expansión de DL en la herramienta de aprovisionamiento de los usuarios.
  
![Herramienta Aprovisionamiento de usuarios donde se muestra la ficha Creación de lista de distribución.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
La ficha lista de distribución permite crear listas de distribución que va a usar la herramienta de rendimiento y esfuerzo para la característica de expansión de lista de distribución. Antes de crear listas de distribución, Skype para Business Server 2015 debe implementarse, incluida la necesidad de ejecutar ForestPrep. Si no se ha hecho esto, los atributos de la lista de distribución no existe en el esquema de Active Directory, por lo que la herramienta no podrá crear listas de distribución.
  
### <a name="to-configure-distribution-lists"></a>Para configurar las listas de distribución:

1. En el campo **Número de listas de distribución** , asigne el número total de listas de distribución que desea crear (aquí la recomendación es que comience con un valor que es el doble del número de usuarios tiene.).
    
2. En el campo **Prefijo de la lista de distribución** , introduzca un prefijo que se va a tener todas las listas de distribución se crea, por ejemplo *testDL* . Esto significa que, en 100 listas de distribución, los nombres de DL tendrá el siguiente aspecto: testDL0, testDL1, hasta testDL99.
    
3. En el campo **Mínimo miembros en una lista de distribución** , escriba el número mínimo de usuarios para poner en cada lista de distribución.
    
4. En el campo **Número máximo de miembros en una lista de distribución** , escriba el número máximo de usuarios para agregar en cada lista de distribución.
    
#### <a name="create-distribution-lists-button"></a>Crear listas de distribución de botón

Al hacer clic en el botón Crear listas de distribución, la herramienta consulta Active Directory para ver si las listas de distribución que coincidan con que el prefijo y los números ya existen. La herramienta crea las listas de distribución que aún no existen. Al agregar miembros a estas recién creado las listas de distribución, elegir los usuarios desde el intervalo especificado en la ficha de creación de usuario.
  
#### <a name="location-info-service-config-tab"></a>Ficha de configuración del servicio de información de ubicación

El Skype para Business Server 2015 herramienta de esfuerzo y rendimiento también puede generar los archivos de configuración ficticio para el servicio de información de ubicación. Tenga en cuenta que el servicio de información de ubicación normalmente no tiene impacto significativas del rendimiento en los servidores. 
  
![Herramienta Aprovisionamiento de usuarios donde se muestra la pestaña Configuración del servicio de información de ubicaciones.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Si decide probar esta característica, rellene los valores en el formulario y haga clic en el botón Generar archivos de configuración de LIS, que va a crear. Llaman a los archivos CSV:
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
Para importar estos archivos en la base de datos LIS usan estos cmdlets de PowerShell:
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Configurar perfiles de usuario
<a name="BKMK_UserProfile"> </a>

Después de que se crean los usuarios (a través de la herramienta de creación de usuario) puede configurar los perfiles de usuario con el Skype para la herramienta de configuración de carga de Business Server 2015 (UserProfileGenerator.exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Ejecuta la Skype para la herramienta de configuración de carga de Business Server 2015

Iniciar la herramienta de configuración de carga (UserProfileGenerator.exe) y rellene las fichas. Esta herramienta crea un directorio para cada uno de los clientes de equipos que necesita ejecutar sus simulaciones. Cada directorio de cliente incluye una secuencia de comandos para iniciar el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento (LyncPerfTool.exe). En las secciones siguientes proporciona ejemplos de cómo rellenar los campos de cada ficha de la Skype para la herramienta de configuración de carga de Business Server 2015.
  
> [!IMPORTANT]
> Los valores específicos del usuario utilizados en la herramienta de configuración de carga (UserProfileGenerator.exe) deben coincidir con los valores especificados en el Skype para la herramienta de creación de Business Server 2015 usuario (UserProvisioningTool.exe) para el grupo de servidores. 
  
#### <a name="common-configuration-tab"></a>Ficha de configuración común

A continuación se muestra la ficha de **Configuración común** de la herramienta de configuración de carga. Rellene los campos de la ficha de configuración común, tal como se describe en los pasos siguientes.
  
![Pestaña Aprovisionamiento de usuarios donde se muestra la pestaña Configuración común.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. En el campo **Número de máquinas disponibles** , escriba el número de equipos que desea usar para ejecutar la herramienta de esfuerzo y rendimiento (LyncPerfTool.exe). Se recomienda que tiene un equipo para cada 4500 usuarios que aquí se simulando, pero ese número puede variar si reducir el nivel de carga, o usar sólo un subconjunto de características disponibles de la herramienta (en la ficha General escenarios se establecen los niveles de carga).
    
2. En el campo **prefijo para los nombres de usuario** , escriba un prefijo para el campo de nombre de usuario de todos los usuarios. Para iniciar sesión en el identificador uniforme de recursos (URI) será: *UserPrefix [usuario iniciar Index... (Número de usuarios-1)] @User dominio* , por ejemplo, myUser009@Contoso.com.
    
3. En el campo **contraseña para todos los usuarios** , escriba la contraseña que se utiliza durante la creación de los usuarios. Si deja este campo en blanco se establecerá el nombre de usuario como la contraseña.
    
4. En el campo de **Índice de inicio del usuario** , escriba el índice del primer usuario que desea configurar. Puede configurar intervalos diferentes para distintos tipos o niveles de carga, pero debe ejecutar la herramienta de configuración de carga (UserProfileGenerator.exe) una vez por el intervalo que desee configurar.
    
5. En el campo **Número de usuarios** , escriba el número total de usuarios que va a configurar.
    
6. En el campo **Dominio de usuario** , escriba el dominio del URI del SIP. Esto se utiliza para construir el URI del SIP de cada usuario para iniciar sesión en el Skype para profesionales de 2015 Front-End Server o servidor Standard Edition y puede ser diferente de la cuenta de dominio.
    
7. En el campo de la **Cuenta de dominio** , escriba el inicio de sesión de dominio de AD DS.
    
8. En el campo **Porcentaje de MPOP** (porcentaje de varios puntos de presencia), proporcionar un valor para el porcentaje de usuarios que han iniciado sesión desde varios equipos o dispositivos, por ejemplo un 10 por ciento.
    
9. Escriba el número máximo de usuarios simultáneos extremos en el campo **iniciar sesión por la segunda (por cada instancia)** . Esto es el máximo número de inicios de sesión para los usuarios y la recomendación es una velocidad menor que o igual a 2 por segundo (< = 2).
    
10. En el campo **servidor Proxy de acceso o el FQDN del grupo de servidores** , escriba el nombre de dominio completo (FQDN) del servidor que desea que los clientes para conectarse a. Si los usuarios inician sesión en externamente, debe escribir al proxy de acceso. Si los usuarios son internos, proporcione el FQDN de su grupo de servidores Enterprise o servidor Standard Edition.
    
11. En el campo **puerto** , especifique el puerto que desea que los usuarios que se usará para SIP (el valor predeterminado es 5061).
    
12. Para el campo de la **Configuración del servidor de red externo** , proporcione el Proxy de acceso o FQDN del grupo de servidores y, de nuevo, el **puerto**. Estas opciones se usan únicamente para simulación de carga de extremos externos.
    
#### <a name="general-scenarios-tab"></a>Ficha General escenarios

![Herramienta de configuración de carga donde se muestra la ficha Escenarios generales.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Puede configurar los parámetros y los niveles de carga para cada uno de los escenarios generales que ofrece mediante la determinación de qué desea ejecutar o deje deshabilitado. Estas son las opciones generales:
  
> [!NOTE]
> Valores de nivel de carga para todos los campos excepto los servicios locales de información están **deshabilitados**, **baja**, **Media**, **alta**o **personalizada**. Si selecciona cualquier opción pero deshabilitados, las configuraciones se generan para cada cliente. Resultados de alta en la carga máxima admitido en el servidor; medio es 60% de carga alta; bajo es 30%. 
  
- **Mensajería instantánea:** Esto incluye punto a punto y conferencias; Elija el valor apropiado para el nivel de carga.
    
- **Conferencias de audio-** Elija un nivel de carga para conferencias de audio *únicamente* . Las llamadas de punto a punto se va a abordar un poco más adelante en la sección de **Escenarios de voz** . Abra la ficha **Opciones avanzadas** para habilitar MultiView.
    
- **Uso compartido de aplicaciones-** Elija un nivel de carga para uso compartido de aplicaciones.
    
- **Colaboración de datos:** Elija un nivel de carga para colaboración de datos, que incluye la conferencia de datos.
    
- **Expansión de la lista de distribución:** Haga clic en el botón **Opciones avanzadas** y rellena el campo con los mismos valores que se configura en la ficha lista de distribución de la herramienta de creación de usuario (UserProvisioningTool.exe). Elija un nivel de carga.
    
- **Consulta Web de libreta de direcciones-** Esto es el servicio de búsqueda de la libreta de direcciones, en lugar de la descarga de archivos de la libreta de direcciones. Si desea habilitar esta opción para descargas de archivo de la libreta de direcciones, haga clic en el botón **Opciones avanzadas** y establecer **EnableABSDownload** en True. Proporcione un valor para el nivel de carga.
    
- **Servicio de grupo de respuesta:** Haga clic en el botón **Opciones avanzadas** y especifique al URI de los grupos de respuesta que ya creó al aprovisionar los agentes del servicio de grupo de respuesta. Debe elegir al menos un grupo de respuesta. Para usar más información, separe los grupos de respuesta con punto y coma. Actualice **RGSUriSuffixStartIndex** y **RGSUriSuffixEndIndex** a los valores reales. Elija un nivel de carga.
    
- **Servicios de información de ubicación:** Seleccione un nivel de carga de habilitado o deshabilitado.
    
> [!NOTE]
> Cada uno de los escenarios tiene un botón avanzadas que se encuentra junto a la base de datos y un conjunto de casillas de verificación que les permiten a las variaciones en el valor predeterminado. 
  
- Elección de *Ad-hoc* le permitirá la herramienta generar la simulación de conferencias que se crearán a lo largo de la hora.
    
- Si selecciona *Conf grande* significa que se deben simular en un escenario de conferencia grande.
    
-  *Externo* , indica a la herramienta para simular también los usuarios externos.
    
Estas casillas de verificación y los botones son valores adicionales específicos para cada escenario y va a cambiar el comportamiento de la herramienta de rendimiento y esfuerzo y permiten la personalización.
  
Para cada escenario en la ficha General escenarios (excepto por los servicios de información de ubicación), si el valor de nivel de carga es **personalizada**, a continuación, la tasa de conversación se calcularán utilizando el campo correspondiente en el cuadro de diálogo Opciones avanzadas. El nombre de campo puede diferir, dependiendo del escenario, pero la descripción del campo se de estado: *Nota: este número solo se usará si se selecciona personalizado en el menú desplegable* .
  
Los valores de **alta**, **Media**y **baja**, modificará las tasas de conversación por modalidad en línea con el modelo de usuario que es un equilibrio de todos los escenarios. Si no hay necesidad de cambiar el nivel de carga por modalidad debido a una diferencia en uso esperado, utilice una velocidad de conversación personalizada.
  
#### <a name="voice-scenarios-tab"></a>Ficha de escenarios de voz

Ésta es la ficha para la configuración de todos los escenarios de relacionadas con la voz.
  
![Herramienta de configuración de carga, ficha Escenarios de voz.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Las opciones son:
  
- **VoIP-** Haga clic en el botón **Opciones avanzadas** y agregue los valores de los campos de PhoneAreaCode y LocationProfile (plan de marcado). También deberá dar a un valor para el nivel de carga. Si elige un nivel de carga para VoIP o UC o puerta de enlace RTC habilitada, a continuación, una red telefónica pública conmutada (RTC) para las comunicaciones unificadas (UC) se generará el archivo de configuración para simular las llamadas externas.
    
- **Puerta de enlace de RTC/UC-** Debe elegir un valor de nivel de carga, y al elegir algo distinto de deshabilitado, también tiene que proporciona un valor para el código de área de RTC haciendo clic en el botón **Avanzadas** . Haga clic en **Agregar** en el servidor de mediación y la RTC. Asegúrese de que tiene una ruta configurada para el código de área.
    
    > [!TIP]
    > Puede usar cualquiera el Skype para el Panel de Control o Skype para el Shell de administración empresarial para comprobar la configuración de ruta de voz. 
  
- **Operador de conferencia:** Proporcionar un valor para el nivel de carga. Cualquier valor distinto de deshabilitado habilitará el campo **Número de teléfono** . Escriba el número de teléfono del operador automático que desea usar. Haga clic en **Avanzadas** y proporcionar un valor para el campo **LocationProfile** .
    
- **Llame al servicio de estacionamiento-** En este caso, proporcionar un nivel de carga.
    
- **Servidor de mediación y RTC-** Cada servidor de mediación que desea usar necesita su propio simulador de RTC. Una vez que haya determinado de cliente que va a usar para el simulador, configuración de su servidor de mediación para enrutar llamadas a ese equipo en el simulador de RTC configurado. Haga clic en el botón **Agregar** para configurar un valor para el servidor de mediación.
    
    > [!NOTE]
    > Cada escenario tiene un botón avanzadas que se encuentra junto a ella. Cuadros de diálogo Opciones avanzadas contienen la configuración específica de cada escenario que cambia el comportamiento de la herramienta de rendimiento y esfuerzo y permiten la personalización. > para cada escenario en la ficha de escenarios de voz, si el valor de nivel de carga es **personalizada**y, a continuación, la tasa de conversación se calcularán mediante el campo correspondiente en el cuadro de diálogo Opciones avanzadas. El nombre de campo puede diferir, dependiendo del escenario, pero la descripción del campo se de estado: *Nota: este número solo se usará si se selecciona personalizado en el menú desplegable* .
  
#### <a name="web-app-tab"></a>Ficha de aplicación Web

![Herramienta de configuración de carga, ficha Aplicación web.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Aplicación Web es compatible con escenarios de conferencia a través del servidor de la API de Web de comunicaciones unificadas (UCWA) que se instala en un servidor Front-End. Utilice la ficha de la aplicación Web para configurar todos los escenarios de relacionadas con la aplicación web. Las opciones son:
  
- **Configuración de aplicación Web de general-** Haga clic en el botón de **Opciones adicionales** y establecer el **ReachTargetServerUrl** a la IP virtual del grupo de Active Directory (VIP) del grupo de servidores Front-End VIP.
    
- **Uso compartido de aplicaciones-** Seleccione un valor para el nivel de carga.
    
- **Colaboración de datos:** Seleccione un valor para el nivel de carga.
    
- **Mensajería instantánea:** Seleccione un valor para el nivel de carga.
    
- **Conferencias de voz-** Seleccione un valor para el nivel de carga.
    
> [!NOTE]
> Cada uno de los escenarios tiene un botón de **Opciones avanzadas** que se encuentra junto a ella. Cuadros de diálogo avanzados contienen valores específicos para cada escenario que se va a cambiar el comportamiento de la herramienta de rendimiento y esfuerzo y habilitar customization.> para cada uno de los escenarios de la aplicación Web, si el nivel de carga es **personalizada**, a continuación, el valor especificado en el ** ConversationsPerHour** campo se usa en lugar del predeterminado.
  
#### <a name="mobility-tab"></a>Ficha de movilidad

Use esta ficha para configurar todos los escenarios relacionados con la movilidad.
  
![Herramienta de configuración de carga, pestaña Movilidad.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Las opciones aquí son:
  
- **Configuración de movilidad general:** Haga clic en **Configuración adicional** y establezca el campo UcwaTargetServerUrl en la IP virtual (VIP) del grupo de Director o el grupo de servidores Front-End VIP.
    
- **Presencia y mensajería instantánea de P2P/Audio-** Seleccione un valor para el nivel de carga habilitar la simulación de movilidad.
    
> [!NOTE]
> Cada uno de los escenarios tiene un botón de **Opciones avanzadas** que se encuentra junto a ella. Cuadros de diálogo avanzados contienen valores específicos para cada escenario que se va a cambiar el comportamiento de la herramienta de rendimiento y esfuerzo y habilitar customization.> para cada uno de los escenarios de movilidad, si el nivel de carga es **personalizada**, a continuación, el valor especificado en el ** ConversationsPerHour** campo se usa en lugar del predeterminado.
  
#### <a name="summary-tab"></a>Ficha Resumen

La ficha Resumen indica los usuarios que se debe usar para cada uno de los escenarios.
  
![Herramienta de configuración de carga, ficha Resumen.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
La ficha Resumen indica los usuarios que se debe usar para cada uno de los escenarios. 
  
Es posible configurar manualmente los intervalos de números de usuario mediante la selección de la casilla de verificación **Habilitar la generación de intervalo de usuario personalizada** y, a continuación, haga doble clic en el escenario en la tabla que tiene el intervalo de usuario que desea personalizar.
  
Comprobar **(RunClient.bat) agregar inicio de sesión de retraso al iniciar** para incluir los retrasos en los archivos por lotes generado para que se corresponda con la tasa de inicio de sesión. Esto es útil para evitar la sobrecarga del servidor al iniciar sesión en un gran número de usuarios.
  
Haga clic en **Generar archivos** y seleccione la carpeta donde desea generar la configuración. Cuando los archivos se han creado correctamente, aparecerá un cuadro de diálogo.
  
![Cuadro de mensaje “Archivos de configuración de carga generados correctamente”. Haga clic en Aceptar.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Ejecute LyncPerfTool
<a name="BKMK_RunTool"> </a>

Debe crear los usuarios, contactos y escenarios antes de ejecutar el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento (LyncPerfTool.exe). Para obtener información detallada sobre el uso de las herramientas para realizar estas acciones, vea [crear usuarios y contactos](using-the-tool.md#BKMK_CreateUsersAndContacts) y [Configurar perfiles de usuario](using-the-tool.md#BKMK_UserProfile) anteriormente en este artículo. Ejecución de estas herramientas también generará un archivo que se ejecutará con los parámetros necesarios que se incluye con la herramienta de esfuerzo y rendimiento como parte de un archivo por lotes.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Ejecuta la Skype para herramienta Business Server 2015 Stress and Performance

La herramienta de configuración de carga (UserProfileGenerator.exe) crea un archivo por lotes que le permite ejecutar la herramienta de esfuerzo y rendimiento (LyncPerfTool.exe) mediante el registro de contadores de rendimiento y carga el archivo de configuración XML. El archivo por lotes ejecuta una instancia de LyncPerfTool.exe por el archivo de configuración. Para ejecutar el archivo por lotes siga estos pasos:
  
### <a name="run-the-stress-and-performance-test"></a>Ejecute la prueba de esfuerzo y rendimiento

1. Copie la carpeta con los archivos dentro de las carpetas de configuración en el directorio que tiene LyncPerfTool.exe en cada equipo cliente. (Por ejemplo, si genera los archivos de configuración en la carpeta denominada 1.28_13.16.16, copie esa carpeta a la carpeta con LyncPerfTool.exe en ella. Hacer esto en cada cliente.)
    
2. Navegue a la carpeta de cliente y ejecute la secuencia de comandos de proceso por lotes **RunClient** . Haga doble clic en el archivo por lotes en el Explorador de Windows y se ejecutará todos los archivos de configuración para que el cliente. También puede ejecutar el script desde una carpeta de cliente mediante el uso de la sintaxis siguiente:
    
   ```
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Para ejecutar la herramienta de esfuerzo y rendimiento directamente, abra un símbolo del sistema y escriba el comando siguiente en la línea de comandos (y al hacerlo por primera vez, asegúrese de registrar los contadores de rendimiento `regsvr32 /i /n /s LyncPerfToolPerf.dll`, como se muestra en la nota más adelante en este tema):
  
```
LyncPerfTool.exe /file:IM_client0.xml
```

Para que la herramienta mostrar los valores en el archivo de configuración, incluir la `/displayfile` parámetro en el comando anterior, por lo que TI tiene este aspecto:
  
```
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Al *final* del proceso, presione CTRL+c.
  
> [!NOTE]
> Antes de ejecutar la herramienta de esfuerzo y rendimiento directamente, debe registrar los contadores de rendimiento mediante el siguiente comando:`regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Cada instancia de la herramienta de esfuerzo y rendimiento que inicie comenzará inmediatamente a iniciar la sesión de los usuarios, normalmente en una tasa de un usuario por segundo. 
  
La velocidad de inicio de sesión del usuario de máxima para el grupo de servidores es aproximadamente 12 por segundo. Esto significa que no debe iniciar instancias de más de 12 LyncPerfTool.exe al mismo tiempo mientras los usuarios aún son iniciar sesión. Los usuarios a miles de ellas tardarán aproximadamente 20 minutos para totalmente suscribirse a uno por segundo.
  
## <a name="interpreting-the-results"></a>Interpretar los resultados
<a name="BKMK_Interpret"> </a>

El Skype para Business Server 2015 herramienta de esfuerzo y rendimiento tiene muchos contadores que le ayudarán a comprender lo que está haciendo el cliente y, si se produzcan problemas.
  
### <a name="client-counters"></a>Contadores de cliente

Cada instancia de LyncPerfTool.exe que ejecuta tiene una instancia independiente de los contadores. Cada instancia se denomina por su identificador de proceso. Si los clientes están sobrecargados pueden producirse otros problemas. Para evitar estos problemas:
  
- Supervisar el uso de CPU y memoria en los equipos cliente. Si es siempre por encima del 90 por ciento de la CPU, reducir el número de usuarios.
    
- Cuando el consumo de memoria es alto, es posible que ejecute en problemas si el archivo de página comienza a quedarse sin espacio. Compruebe que la carga de transacciones no está alcanzando el límite en el equipo. Si se ejecuta en los límites de memoria tenga en cuenta el aumento del tamaño de archivo de página o reducir el número de usuarios.
    
Aquí tiene una lista de contadores de rendimiento clave:
  
**Información general**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Tiempo empleado en minutos  <br/> |Tiempo empleado en desde que se inició el proceso.  <br/> |
|Extremos de activos  <br/> |Número de extremos que actualmente está conectado al servidor.  <br/> |
|Inicios de sesión con errores  <br/> |Número total de errores de inicio de sesión de extremo.  <br/> |
|Intentos de inicio de sesión  <br/> |Número total de intentos de inicio de sesión de extremo.  <br/> |
|Extremos desconectados  <br/> |Número total de extremos que se han desconectado.  <br/> |
   
**Información de presencia**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas de SetPresence  <br/> |Número total de presencia cambie intentos. Para distintos tipos de cambios de presencia, vea el contador de rendimiento de las llamadas de SetPresence (tipo de presencia).  <br/> |
|Respuestas en NNN SetPresence  <br/> |Número total de los códigos de respuesta nnn recibido desde el servidor.  <br/> |
|Llamadas de GetPresence  <br/> |Número total de intentos de solicitud de presencia de get.  <br/> |
|Respuestas en NNN GetPresence  <br/> |Número total de los códigos de respuesta nnn recibido desde el servidor.  <br/> |
   
**Información de servicio de la libreta de direcciones**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Descargas de archivos ABS completo/Delta intentadas  <br/> |Número total de completa o delta solicitudes de descarga de archivos ha intentado.  <br/> |
|Descargas de archivo ABS completo/Delta con resultados  <br/> |Número total de completa o delta solicitudes de descarga de archivos ha intentado.  <br/> |
|Consulta Web de libreta de direcciones contadores relacionados con el servicio  <br/> |Archivo de la libreta de direcciones descargar contadores relacionados.  <br/> |
|Llamadas de WS ABS intentado  <br/> |Número total de solicitudes de servicio de consulta Web de libreta de direcciones ha intentado.  <br/> |
|Llamadas de WS ABS se ha realizado correctamente  <br/> |Número total de solicitudes de servicio de consulta Web de libreta de direcciones que devuelven un código de respuesta es correcta.  <br/> |
|Error en las llamadas de WS de ABS  <br/> |Número total de solicitudes de servicio de consulta Web de libreta de direcciones que ha devuelto un código de respuesta de error.  <br/> |
   
> [!NOTE]
> Esta categoría incluye contadores para supervisar las descargas de archivos de la libreta de direcciones (ABS) de servicio y las solicitudes de servicio de consulta Web de libreta de direcciones. 
  
**Información de distribución (DL) de la lista**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Ha tratado de las llamadas  <br/> |Número total de solicitudes de servicio de web en expansión (DLX) de distribución lista ha intentado.  <br/> |
|Llamadas se ha realizado correctamente  <br/> |Número total de solicitudes de servicio web DLX que devuelven un código de respuesta es correcta.  <br/> |
|Llamadas no se pudo  <br/> |Número total de solicitudes de servicio web DLX que devuelven un código de respuesta de error.  <br/> |
   

  
> [!NOTE]
> Los contadores de rendimiento que aparecen debajo de los números de informe de voz todos los a través de las llamadas IP (VoIP), incluidas las llamadas al servidor de mediación, A / aplicación V Conferencing Server, perimetral Server, grupo de respuesta y operador automático de conferencia, cuando están habilitados estos escenarios. 
  
**Información de VoIP Basic**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de voz entrantes o salientes llamadas curso actualmente.  <br/> |
|Llamadas terminadas  <br/> |Número total de llamadas de voz entrantes o salientes ya finalizado.  <br/> |
|Llamadas rechazadas  <br/> |Número total de llamadas de voz entrantes rechazadas.  <br/> |
|Ha tratado de las llamadas entrantes o salientes  <br/> |Número total de llamadas de voz entrantes o salientes intentado.  <br/> |
|Establecidas las llamadas entrantes o salientes  <br/> |Número total de llamadas de voz entrantes o salientes establecido.  <br/> |
|Las llamadas recibidas NNN  <br/> |Número total de los códigos de respuesta nnn recibido desde el servidor.  <br/> |
|Tasa de Pass VoIP (%)  <br/> |Total de llamadas de llamadas de establecido/Total ha intentado.  <br/> |
   
**Servicio de grupo de respuesta de información de llamadas**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas activas a la aplicación de grupo de respuesta.  <br/> |
|Ha tratado de las llamadas  <br/> |Número total de llamadas que se ha tratado.  <br/> |
   
**Información de la llamada (IM) de mensajería instantánea**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas de mensajería instantáneas entrantes o salientes continuadas.  <br/> |
|Llamadas terminadas  <br/> |Número total de llamadas de mensajería instantáneas entrantes o salientes ya finalizado.  <br/> |
|Las llamadas recibidas NNN  <br/> |Número total de los códigos de respuesta nnn recibido desde el servidor.  <br/> |
|Mensajes Instantáneos recibidos/enviados  <br/> |Número total de mensajes recibidos o enviados para todas las sesiones.  <br/> |
|Ha tratado de las llamadas entrantes o salientes  <br/> |Número total de entrantes o salientes instantáneas mensajería llamadas ha intentado.  <br/> |
|Establecidas las llamadas entrantes o salientes  <br/> |Número total de llamadas de mensajes instantáneos entrantes o salientes establecido.  <br/> |
   
**Información de llamada de una aplicación de uso compartido**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas de uso compartido de aplicación continuada entrantes o salientes.  <br/> |
|Llamadas terminadas  <br/> |Número total de aplicación entrantes o salientes de las llamadas de uso compartido ya finalizado.  <br/> |
|Las llamadas recibidas NNN  <br/> |Número total de los códigos de respuesta nnn recibido desde el servidor.  <br/> |
|Ha tratado de las llamadas entrantes o salientes  <br/> |Número total de uso compartido ha tratado de las llamadas de aplicaciones entrantes o salientes.  <br/> |
|Establecidas las llamadas entrantes o salientes  <br/> |Número total de llamadas establecidas el uso compartido de aplicación entrantes o salientes.  <br/> |
   
**Información de llamada CAA**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de entrantes o salientes de red telefónica conmutada (RTC) llamadas curso actualmente.  <br/> |
|Llamadas terminadas  <br/> |Número total de llamadas entrantes o salientes de RTC ya finalizado.  <br/> |
|Ha tratado de las llamadas entrantes o salientes  <br/> |Número total de las llamadas RTC entrantes o salientes intentado.  <br/> |
|Establecidas las llamadas entrantes o salientes  <br/> |Número total de las llamadas RTC entrantes o salientes establecido.  <br/> |
   
**Información de conferencia**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Conferencias de mensajería instantáneas activas  <br/> |Número total de conferencias mensajería instantáneas en curso.  <br/> |
|Conferencias de Audio y vídeo activas  <br/> |Número total de audio y vídeo continuada (A / V) las conferencias.  <br/> |
|Conferencias de uso compartido de aplicación activa  <br/> |Número total de conferencias de uso compartido continuo de las aplicaciones.  <br/> |
|Número de participantes  <br/> |Número total de participantes conectado actualmente a las conferencias.  <br/> |
|Error de programación de conferencia  <br/> |Número total de errores al intentar programar una conferencia.  <br/> |
|Unirse a conferencia error  <br/> |Número total de errores al intentar conectarse a una conferencia.  <br/> |
   
**Contadores de cliente UCWA**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Número total de IMMCU se une a correcta  <br/> |Número total de conferencias de mensajería instantáneas se unió a.  <br/> |
|Número total de DMCU se une a correcta  <br/> |Número total de A / unido las conferencias de audio.  <br/> |
   

