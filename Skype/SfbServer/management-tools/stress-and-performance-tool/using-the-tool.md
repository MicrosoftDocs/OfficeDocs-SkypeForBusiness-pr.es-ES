---
title: Usar la herramienta de estrés y rendimiento de Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: Para ejecutar la herramienta de estrés y rendimiento de Skype empresarial Server 2015, tendrá que poder administrar los usuarios, los contactos y los perfiles de usuario, configurar la herramienta para ejecutar y, a continuación, revisar los resultados generados por la herramienta.
ms.openlocfilehash: 9920eb446452b9df23470a46c16eab754cc91577
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816149"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Usar la herramienta de estrés y rendimiento de Skype empresarial Server 2015
 
Para ejecutar la herramienta de estrés y rendimiento de Skype empresarial Server 2015, tendrá que poder administrar los usuarios, los contactos y los perfiles de usuario, configurar la herramienta para ejecutar y, a continuación, revisar los resultados generados por la herramienta.
  
Hay cuatro áreas relacionadas con la herramienta de estrés y rendimiento de Skype empresarial Server 2015 (el archivo ejecutable es LyncPerfTool. exe):
  
- [Crear usuarios y contactos](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurar Perfil de usuario](using-the-tool.md#BKMK_UserProfile)
    
- [Ejecutar LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpretación de los resultados](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Crear usuarios y contactos
<a name="BKMK_CreateUsersAndContacts"> </a>

Debe usar la herramienta de aprovisionamiento de usuarios de Skype empresarial Server 2015 (SB 2015) (UserProvisioningTool. exe) para crear usuarios y contactos para sus pruebas de estrés y rendimiento.
  
Esta es una lista de términos útiles que pueden ser útiles a medida que lee los temas:
  
- **Unidad organizativa** : la unidad organizativa (OU) de servicios de dominio de Active Directory (AD DS).
    
- **Federado/grupo cruzado** : usuarios que pueden comunicarse con los usuarios de otros servicios de mensajería instantánea (mi).
    
- **Listas de distribución o listas de distribución** . Estos son objetos de AD DS que contienen una lista de usuarios de AD DS. Se usan para facilitar la comunicación entre grupos de personas.
    
- **Servicio de información de ubicación** : el servicio de Skype empresarial Server 2015 que, cuando está habilitado y configurado por teléfono, permite la recuperación de la ubicación física de los servicios mejorados de 911 (E911).
    
- **Números de teléfono de Estados Unidos** : números de teléfono asignados al usuario además del URI del SIP que se usa para el enrutamiento de llamadas entrantes y salientes en búsqueda de números invertidas (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Crear usuarios y contactos con UserProvisioningTool. exe

> [!NOTE]
> Antes de empezar, asegúrese de que ha iniciado sesión como miembro del grupo de seguridad administradores de dominio para ejecutar esta herramienta. Tiene que hacer esto porque va a crear usuarios de Active Directory. 
  
Debe usar la herramienta de aprovisionamiento de usuarios de Skype empresarial Server para crear usuarios y contactos para simulación de carga.
  
La **herramienta de aprovisionamiento de usuarios de Skype empresarial Server** se instala con el paquete de herramientas de **estrés y rendimiento de Skype empresarial Server** . Asegúrese de que el instalador del paquete (CapacityPlanningTool. msi) se ha ejecutado en el servidor front-end o en el servidor Standard Edition que desea probar.
  
Para iniciar la herramienta de aprovisionamiento de usuarios de Skype empresarial Server, ejecute el archivo UserProvisioningTool. exe (que se encuentra en% InstalledDirectory% LyncStressAndPerfTool \ LyncStress) en el servidor front-end o en el servidor Standard Edition.
  
> [!IMPORTANT]
> Cuando cree un gran número de usuarios (por ejemplo, 10.000 o más), ejecute el UserProvisioningTool. exe. Tendrá que hacer esto porque la herramienta creará y configurará *nuevos* usuarios de ad.
  
Cuando se abra la herramienta de aprovisionamiento de usuarios, haga clic en configuración y seleccione la configuración de carga. 
  
Para empezar a configurar usuarios y contactos, cargue el archivo predeterminado incluido con el paquete, denominado "SampleData. xml". Esto rellenará previamente los campos con datos de ejemplo que necesitará cambiar para que sea relevante para su implementación.
  
Si tiene un archivo XML preconfigurado que ya contiene la configuración personalizada, puede cargarlo en su lugar. Rellene los campos de la herramienta de aprovisionamiento de usuarios, tal y como se describe en las secciones siguientes.
  
### <a name="to-configure-server-options"></a>Para configurar las opciones del servidor:

1. En el campo **FQDN del grupo de servidores front-end** , escriba el nombre de dominio completo (FQDN) del servidor Standard Edition o el grupo de aplicaciones para el usuario en el que desea hospedar los usuarios.
    
2. En el campo **Prefijo de nombre de usuario** , escriba un prefijo que desee usar para deshacer los nombres de usuario con el fin de realizar pruebas (como "TestUser").
    
3. En el campo **contraseña** , escriba una contraseña que se usará en todas las cuentas de usuario de prueba.
    
4. En el campo dominio de la **cuenta** , escriba el nombre de dominio de su dominio de ad actual (el nombre en el que desea crear los usuarios de prueba).
    
5. En el campo **unidad organizativa** , escriba el nombre del dominio de AD en el que desea crear los usuarios de prueba. (Si la OU ya no existe, se creará para usted).
    
6. En el campo **código de área** , escriba el código de área de tres dígitos que se va a usar en todas las cuentas de usuario de prueba. Asegúrate de que el código de área que elegiste no entre en conflicto con los códigos de área de otros usuarios de AD.
    
7. Haga clic para activar la casilla de verificación **voz habilitada** , si desea habilitar los usuarios de prueba de telefonía IP empresarial.
    
8. En el campo **número de usuarios** , asigne el número total de usuarios de prueba que desea crear.
    
9. En el campo **Índice de inicio** , indique el número de inicio que se usará como sufijo para el prefijo del nombre de usuario (por ejemplo, el prefijo es "TestUser" y el nombre terminará en "0" en el ejemplo siguiente).
    
     ![Herramienta de aprovisionamiento de usuarios donde se muestra la ficha Creación de usuario.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Botón crear usuarios

Al hacer clic en el botón **crear usuarios** , se validan los parámetros de entrada que ha introducido. Si hay algún error de validación, se le preguntará si desea corregirlo. O bien, si todos los valores son correctos, los usuarios comenzarán a aparecer en AD (en la OU que haya especificado). Verá una barra de progreso en la parte inferior de la herramienta mientras se ejecuta. No cierre la aplicación mientras la barra de progreso esté activa.
  
La creación del usuario lleva tiempo, por lo que debe planificar según corresponda. Este proceso puede tardar entre varios minutos para unos pocos usuarios, a unas pocas horas para un gran número de usuarios.
  
Si no tiene acceso al controlador de dominio de AD en su entorno de prueba, puede validar la creación de usuarios iniciando sesión como uno de los usuarios en el intervalo de usuarios que ha especificado para crear. Recuerde usar el prefijo y el sufijo, junto con el @sipDomain como nombre de usuario. Este es un ejemplo: <em>TestUser20@contoso.net</em> .
  
> [!NOTE]
> Si los usuarios ya existen, hacer clic en el botón crear usuarios los actualizará con los cambios de configuración. 
  
#### <a name="delete-users-button"></a>Botón eliminar usuarios

Al hacer clic en el botón **eliminar usuarios** , se validan los parámetros de entrada de la pestaña. Si hay errores de validación, se le pedirá que los corrija y, si los valores de entrada son correctos, los usuarios de prueba especificados se deshabilitarán y eliminarán de Active Directory. Una vez más, aparecerá una barra de progreso en la parte inferior de esta pestaña y no se debe cerrar la aplicación mientras esté activa la barra de progreso.
  
> [!NOTE]
> Solo se admiten números de teléfono con formato estadounidense. Los números de teléfono siempre se asignan a los usuarios y todos los usuarios creados por UserProvisioningTool. exe están habilitados para telefonía IP empresarial de forma predeterminada. Cualquier escenario que use el número de teléfono, como el operador automático de la Conferencia o las llamadas UC-RTC, use este número de teléfono para enrutar las llamadas correctamente. Por esta razón, *todos los usuarios* deben tener un *número de teléfono único* .
  
> [!NOTE]
> **Si tiene que crear dos veces usuarios, el comando fallará a menos que use un código de área diferente o si los usuarios anteriores se han deshabilitado mediante el cmdlet Disable-CsUser.**
  
> [!IMPORTANT]
> Antes de crear contactos, primero debe completar la replicación de usuario (que se realiza desde la pestaña usuarios). 
  
> [!IMPORTANT]
> Si acaba de crear los usuarios, tendrá que esperar hasta que se complete la replicación de Skype empresarial Server y se llenen las cuentas de usuario de la base de datos. **Si los usuarios no han terminado de replicarse, verá un error.** Sabrá Cuándo los usuarios han terminado de replicar si el servicio frontal de Skype empresarial Server 2015 se ha iniciado o si ejecuta correctamente el cmdlet Get-CsUser en el último usuario del número total que ha especificado.
  
#### <a name="contacts-creation-tab"></a>Ficha creación de contactos

Esta pestaña le permite proporcionar los detalles de los contactos de los usuarios para sus pruebas.
  
![Herramienta Aprovisionamiento de usuarios donde se muestra la pestaña Creación de contenido.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Para configurar los contactos de los usuarios, haga lo siguiente:

1. En el campo **promedio de contactos por usuario** , escriba el número promedio de contactos que se van a rellenar en las listas de contactos de cada usuario.
    
2. Seleccione la casilla **fijo** si desea crear un número igual de contactos para cada usuario. Si desea variar el número de contactos creados para los usuarios, desactive la casilla.
    
3. En el campo **promedio de grupos de contactos por usuario** , escriba el número de grupos de contactos por usuario. Este número debe ser menor que el **promedio de contactos por usuario**.
    
4. En el campo **porcentaje de contactos federado/grupo cruzado** , asigne un número entre 0 y 100. Este porcentaje de contactos se creará con los usuarios federados.
    
5. En el campo **Prefijo de usuario federado/grupo cruzado** , asigne al nombre de usuario los usuarios federados que se agregarán a las listas de contactos de los usuarios locales.
    
6. En el campo **dominio SIP de usuario federado/grupo cruzado** , asigne el nombre de dominio SIP de los usuarios federados.
    
7. En la pestaña **creación de usuario** , asegúrese de que la información es correcta. Los contactos se crearán a partir de los valores de la pestaña creación de usuario.
    
8. Haga clic en **crear contactos** para comenzar la creación de contactos. Este proceso puede demorar varios minutos. Una vez completada, aparecerá un cuadro de diálogo con el mensaje "la operación se completó correctamente". Puede validar los contactos que se crearon iniciando sesión como un usuario creado desde la pestaña creación de usuarios.
    
> [!NOTE]
> Una vez que se crean los contactos, esta herramienta reiniciará todos los servidores front-end en el grupo de destino. Es posible que se tarde más (hasta 2 horas) en iniciarse los servidores front-end, dependiendo de cuántos contactos haya creado esta operación. 
  
#### <a name="distribution-list"></a>Lista de distribución

La herramienta de carga y rendimiento de Skype empresarial Server 2015 puede simular la característica de expansión de la lista de distribución (DL) en el cliente de Skype empresarial 2015. Puede omitir este paso si no tiene previsto habilitar la expansión de DL en la herramienta de aprovisionamiento de usuarios.
  
![Herramienta Aprovisionamiento de usuarios donde se muestra la ficha Creación de lista de distribución.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
La pestaña lista de distribución le permite crear listas de distribución que la herramienta esfuerzo y rendimiento usará para la característica de expansión de la lista de distribución. Antes de crear listas de distribución, es necesario implementar Skype empresarial Server 2015, lo que incluye ejecutar ForestPrep. De lo contrario, los atributos de DL no existirán en el esquema de AD, por lo que la herramienta no podrá crear listas de distribución.
  
### <a name="to-configure-distribution-lists"></a>Para configurar listas de distribución:

1. En el campo **número de listas de distribución** , asigne el número total de listas de distribución que desea crear (esta recomendación es comenzar con un valor que sea el doble que el número de usuarios).
    
2. En el campo **prefijo** de la lista de distribución, escriba un prefijo que tendrá todas las listas de distribución que cree, por ejemplo, *testDL* . Eso significa que, en 100 DLs, los nombres de la DL tendrán el siguiente aspecto: testDL0, testDL1, hasta testDL99.
    
3. En el campo **lista de miembros mínimos de una Dist.** , escriba el número mínimo de usuarios que desea incluir en cada DL.
    
4. En el campo **lista máxima de miembros de una Dist.** , introduzca el número máximo de usuarios que desea agregar en cada DL.
    
#### <a name="create-distribution-lists-button"></a>Botón crear listas de distribución

Al hacer clic en el botón crear listas de distribución, la herramienta consulta Active Directory para ver si ya existen listas de distribución que coincidan con el prefijo y los números. La herramienta crea todas las listas de distribución que aún no existen. Cuando agregue miembros a estas listas de distribución recién creadas, elegirá los usuarios del rango especificado en la pestaña creación de usuario.
  
#### <a name="location-info-service-config-tab"></a>Ficha Configuración del servicio de información de ubicación

La herramienta de estrés y rendimiento de Skype empresarial Server 2015 también puede generar archivos de configuración ficticios para el servicio de información de ubicación. Tenga en cuenta que el servicio de información de ubicación normalmente no tiene un impacto significativo en el rendimiento de los servidores. 
  
![Herramienta Aprovisionamiento de usuarios donde se muestra la pestaña Configuración del servicio de información de ubicaciones.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Si elige probar esta característica, rellene los valores del formulario y haga clic en el botón generar archivos de configuración LIS, que se creará. Archivos CSV llamados:
  
- LIS_Subnet. csv
    
- LIS_Switches. csv
    
- LIS_Ports. csv
    
- LIS_WAP. csv
    
Para importar estos archivos en la base de datos LIS, use estos cmdlets de PowerShell:
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Configurar Perfil de usuario
<a name="BKMK_UserProfile"> </a>

Después de crear los usuarios (a través de la herramienta de creación de usuarios), puede configurar los perfiles de usuario con la herramienta de configuración de carga de Skype empresarial Server 2015 (UserProfileGenerator. exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Ejecución de la herramienta de configuración de carga de Skype empresarial Server 2015

Inicie la herramienta de configuración de carga (UserProfileGenerator. exe) y rellene las pestañas. Esta herramienta crea un directorio para cada uno de los equipos cliente que necesitará para ejecutar las simulaciones. Cada directorio de cliente incluye un script para iniciar la herramienta de estrés y rendimiento de Skype empresarial Server 2015 (LyncPerfTool. exe). En las secciones siguientes encontrará ejemplos de cómo rellenar los campos de cada pestaña de la herramienta de configuración de carga de Skype empresarial Server 2015.
  
> [!IMPORTANT]
> Los valores específicos del usuario que se usan en la herramienta de configuración de carga (UserProfileGenerator. exe) deben coincidir con los valores especificados en la herramienta de creación de usuarios de Skype empresarial Server 2015 (UserProvisioningTool. exe) para el grupo. 
  
#### <a name="common-configuration-tab"></a>Ficha Configuración común

A continuación se muestra la pestaña **configuración común** de la herramienta de configuración de carga. Rellene los campos de la pestaña Configuración común, como se describe en los siguientes pasos.
  
![Pestaña Aprovisionamiento de usuarios donde se muestra la pestaña Configuración común.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. En el campo **número de equipos disponibles** , escriba el número de equipos que desea usar para ejecutar la herramienta esfuerzo y rendimiento (LyncPerfTool. exe). Le recomendamos que tenga un equipo para cada 4500 usuarios que va a simular, pero ese número puede variar si reduce el nivel de carga o usa solo un subconjunto de las características disponibles de la herramienta (los niveles de carga se establecen en la ficha escenarios generales).
    
2. En el campo **Prefijo de nombres de usuario** , escriba un prefijo para el campo Nombre de usuario de todos los usuarios. Para iniciar sesión el identificador uniforme de recursos (URI) será: *UserPrefix [índice de inicio de usuario... (Número de usuarios: 1)] @User dominio* , por ejemplo, myUser009@Contoso.com.
    
3. En el campo **contraseña para todos los usuarios** , escriba la contraseña que se usa durante la creación de los usuarios. Si deja este campo en blanco, el nombre de usuario se establecerá como la contraseña.
    
4. En el campo **Índice de inicio de usuario** , escriba el índice del primer usuario que se va a configurar. Puede configurar diferentes rangos para diferentes tipos o niveles de carga, pero debe ejecutar la herramienta de configuración de carga (UserProfileGenerator. exe) una vez por el intervalo que desee configurar.
    
5. En el campo **número de usuarios** , escriba el número total de usuarios que va a configurar.
    
6. En el campo **dominio de usuario** , escriba el dominio usado para el URI del SIP. Se usa para construir el URI SIP de cada usuario para iniciar sesión en el servidor front-end de Skype empresarial Server 2015 o en el servidor Standard Edition, y puede ser diferente del dominio de la cuenta.
    
7. En el campo dominio de la **cuenta** , escriba el inicio de sesión de dominio de AD DS.
    
8. En el campo **porcentaje MPOP** (múltiplo de punto de presencia múltiple), asigne un valor para el porcentaje de usuarios que han iniciado sesión desde varios equipos o dispositivos, por ejemplo, 10 por ciento.
    
9. Escriba el número máximo de puntos de conexión simultáneos en el campo **iniciar sesión por segundo (por instancia)** . Este es el número máximo de inicios de sesión para los usuarios y la recomendación es una tasa de menos de/igual a 2 por segundo (<= 2).
    
10. En el campo **proxy de acceso o FQDN del grupo** , escriba el nombre de dominio completo (FQDN) del servidor al que desea que se conecten los clientes. Si los usuarios inician sesión de forma externa, tendrá que escribir el proxy de acceso. Si los usuarios son internos, proporcione el FQDN de su grupo de servidores Enterprise o servidor Standard Edition.
    
11. En el campo **Puerto** , escriba el puerto que desea que los usuarios usen para SIP (el valor predeterminado aquí es 5061).
    
12. En el campo de **configuración del servidor de red externo** , asigne al proxy de acceso o al grupo de servidores FQDN y, de nuevo, el **Puerto**. Esta configuración solo se usa para la simulación de carga de puntos de conexión externos.
    
#### <a name="general-scenarios-tab"></a>Ficha escenarios generales

![Herramienta de configuración de carga donde se muestra la ficha Escenarios generales.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Puede configurar los niveles de carga y los parámetros para cada uno de los escenarios generales que se ofrecen determinando lo que desea ejecutar o dejar deshabilitado. Estas son las opciones generales:
  
> [!NOTE]
> Los valores de nivel de carga para todos los campos pero los servicios de información local están **deshabilitados**, **baja**, **media**, **alta**o **personalizada**. Si selecciona cualquier configuración pero se deshabilita, se generará una configuración para cada cliente. El resultado alto es la carga máxima admitida en el servidor. medio es 60% de carga elevada; bajo es 30%. 
  
- **Mensajería instantánea:** Esto incluye los pares de par a par y Conferencia; Elija el valor adecuado para el nivel de carga.
    
- **Audioconferencias:** Elija un nivel de carga para las conferencias de audio *solamente* . Las llamadas de punto a punto se abordarán un poco más adelante en la sección **escenarios de voz** . Abra la pestaña **Opciones avanzadas** para habilitar la vista multivista.
    
- **Uso compartido de aplicaciones** Elija un nivel de carga para compartir aplicaciones.
    
- **Colaboración de datos:** Elija un nivel de carga para la colaboración de datos, que incluye conferencias de datos.
    
- **Expansión de la lista de distribución:** Haga clic en el botón **avanzadas** y rellene el campo con los mismos valores configurados en la ficha dl de la herramienta de creación de usuarios (UserProvisioningTool. exe). Elija un nivel de carga.
    
- **Consulta Web de libreta de direcciones:** Este es el servicio de búsqueda de la libreta de direcciones en lugar de descargar el archivo de la libreta de direcciones. Si desea habilitar esta opción para las descargas de archivos de la libreta de direcciones, haga clic en el botón **avanzadas** y establezca **EnableABSDownload** en true. Asigne un valor para el nivel de carga.
    
- **Servicio de grupo de respuesta:** Haga clic en el botón **avanzadas** y especifique los URI de los grupos de respuesta que ya ha creado al aprovisionar agentes del servicio de grupo de respuesta. Debe elegir al menos un grupo de respuesta. Para usar más, separe los grupos de respuesta con signos de punto y coma. Actualice **RGSUriSuffixStartIndex** y **RGSUriSuffixEndIndex** a los valores reales. Elija un nivel de carga.
    
- **Servicios de información de ubicación-** Seleccione un nivel de carga de habilitado o deshabilitado.
    
> [!NOTE]
> Cada uno de los escenarios tiene un botón Avanzado ubicado junto a él, y un conjunto de casillas que habilitan las variaciones en la configuración predeterminada. 
  
- Elegir *ad-hoc* permite a la herramienta generar una simulación de conferencias que se crearán a lo largo de la hora.
    
- Si elige *conf grande* , se simulará un escenario de conferencia de gran tamaño.
    
-  *Externo* indica a la herramienta que también simula usuarios externos.
    
Estos botones y casillas de verificación son valores adicionales específicos para cada escenario y cambian el comportamiento de la herramienta estrés y rendimiento y hacen posible la personalización.
  
Para cada escenario de la ficha escenarios generales (excepto para servicios de información de ubicación), si el valor de nivel de carga es **personalizado**, la tasa de conversación se calculará con el campo correspondiente en el cuadro de diálogo avanzadas. El nombre del campo puede variar según el escenario, pero la descripción del campo indicará lo siguiente: *este número solo se usará si se selecciona personalizado en el menú* desplegable.
  
Los valores **alto**, **medio**y **bajo**, modificarán las tarifas de conversación por modalidad en línea con el modelo de usuario que es un equilibrio de todos los escenarios. Si es necesario cambiar el nivel de carga por modalidad debido a una diferencia en el uso previsto, use una tarifa de conversación personalizada.
  
#### <a name="voice-scenarios-tab"></a>Pestaña escenarios de voz

Esta es la ficha de configuración de todos los escenarios relacionados con la voz.
  
![Herramienta de configuración de carga, ficha Escenarios de voz.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Las opciones son las siguientes:
  
- **VoIP-** Haga clic en el botón **avanzadas** y agregue valores para los campos PhoneAreaCode y LocationProfile (plan de marcado). También proporcionarás un valor para el nivel de carga. Si elige un nivel de carga para la puerta de enlace VoIP o UC/RTC habilitada, se generará una red de telefonía pública conmutada (RTC) a un archivo de configuración de comunicaciones unificadas (UC) para simular llamadas externas.
    
- **Puerta de enlace UC/RTC:** Debe elegir un valor de nivel de carga y, si elige algo distinto de deshabilitado, también tendrá que suministrar un valor para el código de área RTC haciendo clic en el botón **avanzadas** . Haga clic en **Agregar** en el servidor de mediación y en la RTC. Asegúrese de que tiene una ruta configurada para el código de área.
    
    > [!TIP]
    > Puede usar el panel de control de Skype para empresas o el shell de administración de Skype empresarial para verificar la configuración de la ruta de voz. 
  
- **Operador de Conferencia:** Proporcione un valor para el nivel de carga. Cualquier valor distinto de deshabilitado habilitará el campo **número de teléfono** . Escriba el número de teléfono del operador automático que desea usar. Haga clic en **avanzadas** y asigne un valor para el campo **LocationProfile** .
    
- **Servicio de estacionamiento de llamadas:** A continuación, proporcione un nivel de carga.
    
- **Servidor de mediación y RTC-** Cada servidor de mediación que desee usar necesita su propio simulador de RTC. Una vez que haya determinado el cliente que va a usar para el simulador, configure el servidor de mediación para que enrute las llamadas a ese equipo en el simulador RTC que ha configurado. Haga clic en el botón **Agregar** para configurar un valor para el servidor de mediación.
    
    > [!NOTE]
    > Cada escenario tiene un botón Avanzado ubicado junto a él. Los cuadros de diálogo avanzados contienen opciones específicas para cada escenario que cambian el comportamiento de la herramienta estrés y rendimiento y permiten la personalización. > para cada escenario en la pestaña escenarios de voz, si el valor de nivel de carga es **personalizado**, la tasa de conversaciones se calculará usando el campo correspondiente en el cuadro de diálogo Opciones avanzadas. El nombre del campo puede variar según el escenario, pero la descripción del campo indicará lo siguiente: *este número solo se usará si se selecciona personalizado en el menú* desplegable.
  
#### <a name="web-app-tab"></a>Pestaña de la aplicación Web

![Herramienta de configuración de carga, ficha Aplicación web.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App admite escenarios de conferencia a través del servidor API Web de comunicaciones unificadas (UCWA) que se instala en un servidor front-end. Use la pestaña aplicación web para configurar todos los escenarios relacionados con la aplicación Web. Las opciones son las siguientes:
  
- **Configuración general de la aplicación web:** Haga clic en el botón **configuración adicional** y configure el **ReachTargetServerUrl** en la dirección IP virtual (VIP) del grupo de directorios de la VIP del grupo de servidores front-end.
    
- **Uso compartido de aplicaciones** Seleccione un valor para el nivel de carga.
    
- **Colaboración de datos:** Seleccione un valor para el nivel de carga.
    
- **Mensajería instantánea:** Seleccione un valor para el nivel de carga.
    
- **Conferencias de voz:** Seleccione un valor para el nivel de carga.
    
> [!NOTE]
> Cada uno de los escenarios tiene un botón **avanzadas** ubicado junto a él. Los cuadros de diálogo avanzados contienen valores específicos para cada escenario que cambiarán el comportamiento de la herramienta estrés y rendimiento y habilitar la personalización. > para cada uno de los escenarios de la aplicación Web, si el nivel de carga es **personalizado**, se usa el valor especificado en el campo **ConversationsPerHour** en lugar del predeterminado.
  
#### <a name="mobility-tab"></a>Ficha movilidad

Use esta pestaña para configurar todos los escenarios relacionados con la movilidad.
  
![Herramienta de configuración de carga, pestaña Movilidad.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Las opciones son las siguientes:
  
- **Configuración general de movilidad:** Haga clic en **configuración adicional** y configure el campo UcwaTargetServerUrl en la dirección IP virtual del grupo de directores (VIP) o en la VIP del grupo de servidores front-end.
    
- **Presencia y mensajería instantánea de P2P** Seleccione un valor para el nivel de carga para habilitar la simulación de movilidad.
    
> [!NOTE]
> Cada uno de los escenarios tiene un botón **avanzadas** ubicado junto a él. Los cuadros de diálogo avanzados contienen valores específicos para cada escenario que cambiarán el comportamiento de la herramienta estrés y rendimiento y permiten la personalización. > para cada uno de los escenarios de movilidad, si el nivel de carga es **personalizado**, se usa el valor especificado en el campo **ConversationsPerHour** en lugar del predeterminado.
  
#### <a name="summary-tab"></a>Pestaña Resumen

La pestaña Resumen indica qué usuarios deben usar para cada uno de los escenarios.
  
![Herramienta de configuración de carga, ficha Resumen.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
La pestaña Resumen indica qué usuarios deben usar para cada uno de los escenarios. 
  
Es posible configurar manualmente los intervalos de número de usuario seleccionando la casilla de verificación **Habilitar la generación de intervalos de usuario personalizada** y, a continuación, hacer doble clic en el escenario de la tabla que tiene el intervalo de usuario que desea personalizar.
  
Comprobar **(RunClient. bat) Agregue la demora de inicio de sesión al iniciarse** para incluir demoras en los archivos por lotes generados para que correspondan a la tasa de inicio de sesión. Esto resulta útil para evitar la sobrecarga del servidor al iniciar sesión en un gran número de usuarios.
  
Haga clic en **generar archivos** y seleccione la carpeta en la que desea generar la configuración. Aparecerá un cuadro de diálogo cuando los archivos se hayan creado correctamente.
  
![Cuadro de mensaje “Archivos de configuración de carga generados correctamente”. Haga clic en Aceptar.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Ejecutar LyncPerfTool
<a name="BKMK_RunTool"> </a>

Tendrá que crear usuarios, contactos y escenarios antes de ejecutar la herramienta de carga y rendimiento de Skype empresarial Server 2015 (LyncPerfTool. exe). Para obtener más información sobre cómo usar las herramientas para realizar estas acciones, consulte [crear usuarios y contactos](using-the-tool.md#BKMK_CreateUsersAndContacts) y [configurar el perfil de usuario](using-the-tool.md#BKMK_UserProfile) anteriormente en este artículo. Al ejecutar estas herramientas, también se generará un archivo que se ejecutará con la herramienta estrés and performance como parte de un archivo por lotes con los parámetros obligatorios incluidos.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Ejecutar la herramienta de estrés y rendimiento de Skype empresarial Server 2015

La herramienta de configuración de carga (UserProfileGenerator. exe) crea un archivo por lotes que le permite ejecutar la herramienta stress and Performance (LyncPerfTool. exe) registrando los contadores de rendimiento y cargando el archivo de configuración XML. El archivo de proceso por lotes ejecuta una instancia de LyncPerfTool. exe por archivo de configuración. Para ejecutar el archivo de proceso por lotes, siga estos pasos:
  
### <a name="run-the-stress-and-performance-test"></a>Ejecutar la prueba de rendimiento y estrés

1. Copie la carpeta con los archivos y las carpetas de configuración en el directorio que tiene LyncPerfTool. exe en cada equipo cliente. (Por ejemplo, si ha generado los archivos de configuración en la carpeta denominada 1.28 _ 13.16.16, copie esa carpeta a la carpeta con LyncPerfTool. exe. Haga esto en cada cliente.)
    
2. Vaya a la carpeta cliente y ejecute el script de proceso por lotes **RunClient** . Puede hacer doble clic en el archivo por lotes en el explorador de Windows y se ejecutarán todos los archivos de configuración de ese cliente. También puede ejecutar el script desde una carpeta de cliente con la siguiente sintaxis:
    
   ```PowerShell
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Para ejecutar la herramienta de estrés y rendimiento directamente, abra un símbolo del sistema y escriba el siguiente comando en la línea de comandos (y, cuando lo haga por primera vez, asegúrese de registrar los contadores de rendimiento `regsvr32 /i /n /s LyncPerfToolPerf.dll`, como se muestra en la nota más adelante en este tema):
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Para que la herramienta muestre los valores en el archivo de configuración, incluya `/displayfile` el parámetro en el comando anterior, de modo que tenga el siguiente aspecto:
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Para *Finalizar* el proceso, presione Ctrl + C.
  
> [!NOTE]
> Antes de ejecutar la herramienta de estrés y rendimiento directamente, debe registrar los contadores de rendimiento mediante el siguiente comando:`regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Cada instancia de la herramienta estrés y rendimiento que inicie iniciará inmediatamente la sesión de los usuarios, generalmente a una tarifa de un usuario por segundo. 
  
La frecuencia máxima de inicio de sesión de usuario para el grupo es de aproximadamente 12 por segundo. Esto significa que no debe iniciar más de 12 instancias de LyncPerfTool. exe al mismo tiempo mientras los usuarios aún están iniciando sesión. 1000 los usuarios tomarán aproximadamente 20 minutos para iniciar sesión por completo a una por una por segundo.
  
## <a name="interpreting-the-results"></a>Interpretación de los resultados
<a name="BKMK_Interpret"> </a>

La herramienta de estrés y rendimiento de Skype empresarial Server 2015 tiene muchos contadores que pueden ayudarle a comprender lo que está haciendo el cliente y si se están encontrando problemas.
  
### <a name="client-counters"></a>Contadores de cliente

Cada instancia de LyncPerfTool. exe que se ejecuta tiene una instancia independiente de los contadores. Cada instancia se denomina mediante su identificador de proceso. Si se producen otros problemas de los clientes sobrecargados. Para evitar estos problemas:
  
- Supervise el uso de la CPU y la memoria en los equipos cliente. Si la CPU es sistemática por encima del 90 por ciento, reduzca el número de usuarios.
    
- Cuando la superficie de memoria es alta, es posible que tenga problemas si el archivo de paginación comienza a quedarse sin espacio. Compruebe que el cargo de asignación no haya alcanzado el límite en el equipo. Si se encuentran límites de memoria, considere la posibilidad de aumentar el tamaño del archivo de paginación o de reducir el número de usuarios.
    
Aquí tiene una lista de contadores de rendimiento clave:
  
**Información general**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Tiempo invertido en minutos  <br/> |Tiempo transcurrido desde que se inició el proceso.  <br/> |
|Puntos de conexión activos  <br/> |Número de puntos finales conectados actualmente al servidor.  <br/> |
|Inicios de sesión erróneos  <br/> |Número total de errores de inicio de sesión de extremo.  <br/> |
|Intentos de inicio de sesión  <br/> |Número total de intentos de inicio de sesión de punto final.  <br/> |
|Puntos de conexión desconectados  <br/> |Número total de puntos de conexión que se han desconectado.  <br/> |
   
**Información de presencia**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas de SetPresence  <br/> |Número total de intentos de cambio de presencia. Para los distintos tipos de cambios de presencia, vea el contador de rendimiento llamadas de SetPresence (tipo de presencia).  <br/> |
|NNN respuestas para SetPresence  <br/> |Número total de los códigos de respuesta nnn recibidos desde el servidor.  <br/> |
|Llamadas a GetPresence  <br/> |Número total de intentos de solicitud de presencia.  <br/> |
|NNN respuestas para GetPresence  <br/> |Número total de los códigos de respuesta nnn recibidos desde el servidor.  <br/> |
   
**Información del servicio de libreta de direcciones**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Intento de descarga de archivos completo/Delta de ABS  <br/> |Número total de solicitudes de descarga de archivos completas o delta intentadas.  <br/> |
|Descarga de archivo completo/Delta de ABS correctamente  <br/> |Número total de solicitudes de descarga de archivos completas o delta intentadas.  <br/> |
|Contadores relacionados con el servicio de la libreta de direcciones  <br/> |Descarga de archivos de la libreta de direcciones.  <br/> |
|Intentos de llamadas de ABS WS  <br/> |Número total de solicitudes de servicio de consulta Web de la libreta de direcciones intentadas.  <br/> |
|Llamadas ABS WS correctas  <br/> |Número total de solicitudes de servicio de consulta Web de la libreta de direcciones que devolvieron un código de respuesta correcto.  <br/> |
|Error en las llamadas de ABS WS  <br/> |Número total de solicitudes de servicio de consulta Web de la libreta de direcciones que devolvieron un código de respuesta de error.  <br/> |
   
> [!NOTE]
> Esta categoría incluye los contadores usados para supervisar las solicitudes de servicio de descargas de archivos del servicio de libreta de direcciones (ABS) y la libreta de direcciones web de la libreta de direcciones. 
  
**Información de la lista de distribución (DL)**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas intentadas  <br/> |Número total de solicitudes de servicio Web de expansión de la lista de distribución (DLX) intentadas.  <br/> |
|Llamadas correctas  <br/> |Número total de solicitudes de servicio Web de DLX que devolvieron un código de respuesta satisfactorio.  <br/> |
|Error en las llamadas  <br/> |Número total de solicitudes de servicio Web de DLX que devolvieron un código de respuesta de error.  <br/> |
   

  
> [!NOTE]
> Los contadores de rendimiento que aparecen a continuación indican números para todas las llamadas de voz a través de IP (VoIP), incluidas las llamadas a servidor de mediación, el servidor de conferencia a/V, el servidor perimetral, la aplicación de grupo de respuesta y el operador automático de conferencia, cuando se habilitan estos escenarios. 
  
**Información básica de VoIP**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas de voz entrantes y salientes actualmente en curso.  <br/> |
|Llamadas finalizadas  <br/> |Número total de llamadas de voz entrantes y salientes que ya han finalizado.  <br/> |
|Llamadas rechazadas  <br/> |Número total de llamadas de voz entrantes rechazadas.  <br/> |
|Intentos de llamadas entrantes y salientes  <br/> |Número total de llamadas de voz entrantes y salientes intentadas.  <br/> |
|Llamadas entrantes y salientes establecidas  <br/> |Número total de llamadas de voz entrantes y salientes establecidas.  <br/> |
|Llamadas recibidas NNN  <br/> |Número total de los códigos de respuesta nnn recibidos desde el servidor.  <br/> |
|Tasa de transferencia de VoIP (%)  <br/> |Llamadas totales establecidas/llamadas totales realizadas.  <br/> |
   
**Información de llamada del servicio de grupo de respuesta**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas activas a la aplicación de grupo de respuesta.  <br/> |
|Llamadas intentadas  <br/> |Número total de intentos de llamada.  <br/> |
   
**Información de la llamada de mensajería instantánea (mi)**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas entrantes y salientes de mensajería instantánea en curso.  <br/> |
|Llamadas finalizadas  <br/> |Número total de llamadas de mensajería instantánea entrantes o salientes que ya han finalizado.  <br/> |
|Llamadas recibidas NNN  <br/> |Número total de los códigos de respuesta nnn recibidos desde el servidor.  <br/> |
|Mensajes INSTANTÁNEos recibidos/enviados  <br/> |Número total de mensajes recibidos o enviados para todas las sesiones.  <br/> |
|Intentos de llamadas entrantes y salientes  <br/> |Número total de intentos de llamadas entrantes y salientes de mensajes instantáneos.  <br/> |
|Llamadas entrantes y salientes establecidas  <br/> |Número total de llamadas de mensajes instantáneos entrantes o salientes que se han establecido.  <br/> |
   
**Información de llamadas de uso compartido de aplicaciones**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas de uso compartido de aplicaciones entrantes y salientes en curso.  <br/> |
|Llamadas finalizadas  <br/> |Número total de llamadas de uso compartido de aplicaciones entrantes o salientes que ya se han finalizado.  <br/> |
|Llamadas recibidas NNN  <br/> |Número total de los códigos de respuesta nnn recibidos desde el servidor.  <br/> |
|Intentos de llamadas entrantes y salientes  <br/> |Número total de llamadas de uso compartido de aplicaciones entrantes o salientes.  <br/> |
|Llamadas entrantes y salientes establecidas  <br/> |Número total de llamadas de uso compartido de aplicaciones entrantes o salientes establecidas.  <br/> |
   
**Información de la llamada de CAA**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas de red telefónica conmutada (RTC) entrantes y salientes actualmente en curso.  <br/> |
|Llamadas finalizadas  <br/> |Número total de llamadas RTC entrantes y salientes que ya se han finalizado.  <br/> |
|Intentos de llamadas entrantes y salientes  <br/> |Número total de intentos de llamadas RTC entrantes y salientes.  <br/> |
|Llamadas entrantes y salientes establecidas  <br/> |Número total de llamadas RTC entrantes y salientes establecidas.  <br/> |
   
**Información sobre la Conferencia**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Conferencias de mensajería instantánea activas  <br/> |Número total de conferencias de mensajería instantánea en curso.  <br/> |
|Conferencias de audio y vídeo activas  <br/> |Número total de conferencias de audio o vídeo (A/V) en curso.  <br/> |
|Conferencias de uso compartido de aplicaciones activas  <br/> |Número total de conferencias de uso compartido de aplicaciones en curso.  <br/> |
|Número de participantes  <br/> |Número total de participantes actualmente conectados a conferencias.  <br/> |
|Error de programación en Conferencia  <br/> |Número total de errores al intentar programar una conferencia.  <br/> |
|Error al unirse a la Conferencia  <br/> |Número total de errores al intentar conectarse a una conferencia.  <br/> |
   
**Contadores de cliente de UCWA**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Número total de combinaciones de IMMCU correctas  <br/> |Número total de conferencias de mensajería instantánea combinadas.  <br/> |
|Número total de combinaciones de DMCU correctas  <br/> |Número total de conferencias A/V combinadas.  <br/> |
   

