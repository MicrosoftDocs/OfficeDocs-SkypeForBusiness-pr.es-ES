---
title: Uso de la Skype Empresarial Server de esfuerzo y rendimiento de 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Para ejecutar la herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015, deberá poder administrar usuarios, contactos y perfiles de usuario, configurar la herramienta para su ejecución y, a continuación, revisar los resultados o resultados que produce la herramienta.
ms.openlocfilehash: c80f623476bcfd33979256185d87786e2cf92d6b48bc0467dc61c1773569e0fe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283272"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Uso de la Skype Empresarial Server de esfuerzo y rendimiento de 2015
 
Para ejecutar la herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015, deberá poder administrar usuarios, contactos y perfiles de usuario, configurar la herramienta para su ejecución y, a continuación, revisar los resultados o resultados que produce la herramienta.
  
Hay cuatro áreas implicadas en la ejecución de la Skype Empresarial Server 2015 Stress and Performance Tool (el ejecutable es LyncPerfTool.exe):
  
- [Crear usuarios y contactos](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurar perfil de usuario](using-the-tool.md#BKMK_UserProfile)
    
- [Ejecutar LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpretación de los resultados](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Crear usuarios y contactos
<a name="BKMK_CreateUsersAndContacts"> </a>

Debe usar la herramienta de aprovisionamiento de usuarios de Skype Empresarial Server 2015 (SB 2015) (UserProvisioningTool.exe) para crear usuarios y contactos para las pruebas de esfuerzo y rendimiento.
  
Esta es una lista de términos útiles que pueden ser útiles a medida que lee los temas:
  
- **Unidad organizativa:** unidad organizativa (OU) de Servicios de dominio de Active Directory (AD DS).
    
- **Federados o entre grupos:** usuarios que pueden comunicarse con usuarios de otros servicios de mensajería instantánea (MI).
    
- **Listas de distribución:** o DLs. Estos son objetos de AD DS que contienen una lista de usuarios de AD DS. Se usan para facilitar las comunicaciones entre grupos de personas.
    
- **Servicio** de información de ubicación: el servicio Skype Empresarial Server 2015 que, cuando está habilitado y configurado por teléfono, permite recuperar la ubicación física de los servicios mejorados de 911 (E911).
    
- Números de Teléfono **ee.UU.:** números Teléfono asignados al usuario además del URI de SIP que se usa para enrutar llamadas entrantes y salientes en Búsqueda inversa de números (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Crear usuarios y contactos mediante UserProvisioningTool.exe

> [!NOTE]
> Antes de comenzar, asegúrate de haber iniciado sesión como miembro del grupo de seguridad Administradores de dominio para ejecutar esta herramienta. Debe hacerlo, ya que va a crear usuarios de Active Directory. 
  
Debe usar la herramienta de aprovisionamiento Skype Empresarial Server usuario para crear usuarios y contactos para la simulación de carga.
  
La **Skype Empresarial Server de aprovisionamiento de** usuarios se instala con el Skype Empresarial Server de la herramienta de rendimiento y **esfuerzo.** Asegúrese de que el instalador de paquetes (CapacityPlanningTool.msi) se haya ejecutado en el servidor front-end o en el servidor Standard Edition que desea probar.
  
Puede iniciar la herramienta de aprovisionamiento de usuarios de Skype Empresarial Server ejecutando el archivo UserProvisioningTool.exe (ubicado en %InstalledDirectory%LyncStressAndPerfTool\LyncStress) en el servidor front-end o en el servidor Standard Edition.
  
> [!IMPORTANT]
> Al crear un gran número de usuarios (por ejemplo, 10 000 o más), ejecute el UserProvisioningTool.exe. Tendrás que hacerlo porque la herramienta va a crear y configurar  *nuevos*  usuarios de AD.
  
Cuando se abra la Herramienta de aprovisionamiento de usuarios, haga clic en Configuración y seleccione La configuración de carga. 
  
Para empezar a configurar usuarios y contactos, cargue el archivo predeterminado incluido en el paquete, denominado "SampleData.xml". Esto rellenará previamente campos con datos de ejemplo que deberá cambiar para que sean relevantes para la implementación.
  
Si tiene un archivo XML preconfigurado que ya contiene la configuración personalizada, puede cargarlo en su lugar. Rellene los campos de la Herramienta de aprovisionamiento de usuarios, tal como se describe en las secciones siguientes.
  
### <a name="to-configure-server-options"></a>Para configurar las opciones del servidor:

1. En el **campo FQDN** del grupo de servidores front-end, escriba el nombre de dominio completo (FQDN) del servidor Standard Edition o el grupo de servidores front-end donde desea hospedar a los usuarios.
    
2. En el **campo Prefijo de** nombre de usuario, escriba un prefijo que desee usar para romper los nombres de usuario con fines de prueba (como "TestUser").
    
3. En el **campo Contraseña,** escriba una contraseña que se usará en todas las cuentas de usuario de prueba.
    
4. En el **campo Dominio de** cuenta, escriba el nombre de dominio del dominio de AD actual (el que desea crear los usuarios de prueba).
    
5. En el **campo Unidad organizativa,** escriba el nombre del dominio de AD donde desea crear estos usuarios de prueba. (Si la OU aún no existe, se creará automáticamente).
    
6. En el **Teléfono código de área,** escriba el código de área de tres dígitos que se usará en todas las cuentas de usuario de prueba. Asegúrese de que el código de área elegido no entre en conflicto con los códigos de área de otros usuarios en AD.
    
7. Haga clic para activar la **casilla De** voz habilitada, si desea habilitar los usuarios de prueba para Telefonía IP empresarial.
    
8. En el **campo Número de usuarios,** dé el número total de usuarios de prueba que desea crear.
    
9. En el campo **Índice** de inicio, asigne el número inicial que se usará como sufijo al prefijo de nombre de usuario (por ejemplo, el prefijo es "TestUser", y el nombre finalizará en "0" en el ejemplo siguiente).
    
     ![Herramienta de aprovisionamiento de usuarios que muestra la pestaña de creación de usuarios.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Botón Crear usuarios

Al hacer clic en el **botón Crear usuarios,** se validan los parámetros de entrada que ha especificado. Si hay algún error de validación, se le pedirá que los corrija. O bien, si todos los valores son correctos, los usuarios empezarán a aparecer en AD (en cualquier OU que haya especificado). Verá una barra de progreso en la parte inferior de la herramienta mientras se ejecuta. No cierre la aplicación mientras la barra de progreso esté activa.
  
La creación de usuarios lleva tiempo, así que planee según corresponda. Este proceso puede tardar desde varios minutos para unos pocos usuarios hasta unas pocas horas para un gran número de usuarios.
  
Si no tienes acceso al controlador de dominio de AD en el entorno de prueba, puedes validar la creación de usuarios iniciando sesión como uno de los usuarios del rango de usuarios que especificaste para crear. Recuerde usar el prefijo y el sufijo, junto con el @sipDomain como nombre de usuario. Este es un ejemplo:  <em>TestUser20@contoso.net</em>  .
  
> [!NOTE]
> Si los usuarios ya existen, al hacer clic en el botón Crear usuarios, se actualizarán con los cambios de configuración. 
  
#### <a name="delete-users-button"></a>Botón Eliminar usuarios

Al hacer clic en el **botón Eliminar usuarios,** se validarán los parámetros de entrada de la pestaña. Si hay errores de validación, se le pedirá que los corrija y, si los valores de entrada son correctos, los usuarios de prueba especificados se deshabilitarán y eliminarán de Active Directory. De nuevo, aparecerá una barra de progreso en la parte inferior de esta pestaña y no debe cerrar la aplicación mientras la barra de progreso esté activa.
  
> [!NOTE]
> Solo se admiten números de teléfono con formato estadounidense. Teléfono los números siempre se asignan a los usuarios y todos los usuarios creados por UserProvisioningTool.exe están habilitados para Telefonía IP empresarial de forma predeterminada. Cualquier escenario que use el número de teléfono, como conferencias Operador automático o llamadas RTC UC, use este número de teléfono para enrutar correctamente las llamadas. Por este motivo,  *cada usuario*  debe tener un número de *teléfono único*  .
  
> [!NOTE]
> **Si tiene que crear usuarios dos veces, el comando producirá un error a menos que use un código de área diferente o si los usuarios anteriores se han deshabilitado mediante el cmdlet Disable-CsUser.**
  
> [!IMPORTANT]
> Antes de crear contactos, primero debe completar la replicación de usuarios (que se realiza desde la pestaña Usuarios). 
  
> [!IMPORTANT]
> Si acaba de crear los usuarios, tendrá que esperar hasta que Skype Empresarial Server la replicación completa y rellene las cuentas de usuario en la base de datos. **Si los usuarios no han terminado de replicar, verá un error.** Sabrá cuándo los usuarios han terminado de replicar si se ha iniciado el servicio front-end de Skype Empresarial Server 2015 o ejecutando correctamente el cmdlet Get-CsUser en el último usuario del número total especificado.
  
#### <a name="contacts-creation-tab"></a>Pestaña Creación de contactos

Esta pestaña te permite proporcionar los detalles de los contactos de los usuarios para las pruebas.
  
![Herramienta de aprovisionamiento de usuarios que muestra la pestaña Creación de contenido.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Para configurar los contactos de los usuarios, haga lo siguiente:

1. En el **campo Promedio de contactos por usuario,** escriba el número promedio de contactos que se rellenarán en listas de contactos para cada usuario.
    
2. Active la **casilla** Fijo si desea crear un número igual de contactos para cada usuario. Si desea variar el número de contactos creados para los usuarios, desactive esa casilla.
    
3. En el campo Promedio de grupos de contactos **por usuario,** escriba el número de grupos de contactos por usuario. Este número debe ser menor que **el promedio de contactos por usuario**.
    
4. En el **campo Porcentaje de contactos federados/entre** grupo de servidores, dé un número entre 0 y 100. Este porcentaje de contactos se creará con los usuarios federados.
    
5. En el **campo Prefijo de** usuario federado o entre grupos, dé el nombre de usuario para los usuarios federados que se agregarán a las listas de contactos de los usuarios locales.
    
6. En el **campo Dominio SIP de** usuario federado o entre grupos, asigne el nombre de dominio SIP de los usuarios federados.
    
7. En **la pestaña Creación** de usuarios, asegúrese de que la información es correcta. Los contactos se crearán a partir de valores de la pestaña Creación de usuarios.
    
8. Haga **clic en Crear contactos** para iniciar la creación de contactos. Este proceso puede tardar varios minutos. Una vez completado, aparecerá un cuadro de diálogo con el mensaje "Operación completada correctamente". Puede validar los contactos creados iniciando sesión como un usuario que se creó desde la pestaña Creación de usuarios.
    
    > [!NOTE]
    > Una vez creados los contactos, esta herramienta reiniciará todos los servidores front-end del grupo de destino. Los servidores front-end pueden tardar más tiempo (hasta 2 horas) en iniciarse, en función del número de contactos creados por esta operación. 
  
#### <a name="distribution-list"></a>Lista de distribución

La Skype Empresarial Server de esfuerzo y rendimiento de 2015 puede simular la característica de expansión de lista de distribución (DL) en el Skype Empresarial 2015. Puedes omitir este paso si no tienes la intención de habilitar la expansión de DL en la herramienta aprovisionamiento de usuarios.
  
![Herramienta de aprovisionamiento de usuarios que muestra la pestaña Creación de listas de distribución.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
La pestaña Lista de distribución permite crear listas de distribución que usará la Herramienta de esfuerzo y rendimiento para la característica de expansión de listas de distribución. Antes de crear direcciones DLL, Skype Empresarial Server 2015 debe implementarse, incluida la ejecución de ForestPrep. Si esto no se hace, los atributos DL no existirán en el esquema de AD, por lo que la herramienta no podrá crear direcciones URL.
  
### <a name="to-configure-distribution-lists"></a>Para configurar listas de distribución:

1. En el **campo Número** de listas de distribución, indica el número total de direcciones URL que quieres crear (La recomendación aquí es que empieces con un valor que sea el doble del número de usuarios que tienes).
    
2. En el **campo Prefijo de lista de** distribución, escriba un prefijo que tendrán todas las direcciones URL que cree, por ejemplo *testDL*  . Esto significa que, con 100 DLs, los nombres de DL tendrán el aspecto siguiente: testDL0, testDL1, hasta testDL99.
    
3. En el **campo Miembros mínimos de una** lista dist. Escriba el número mínimo de usuarios que se deben colocar en cada DL.
    
4. En el campo Máximo de miembros en una lista **dist.** Escriba el número máximo de usuarios que se agregarán en cada DL.
    
#### <a name="create-distribution-lists-button"></a>Botón Crear listas de distribución

Al hacer clic en el botón Crear listas de distribución, la herramienta consulta Active Directory para ver si las listas de distribución que coinciden con el prefijo y los números ya existen. La herramienta crea cualquier DLs que aún no existe. Al agregar miembros a estas listas de distribución recién creadas, elegirá los usuarios del intervalo especificado en la pestaña Creación de usuarios.
  
#### <a name="location-info-service-config-tab"></a>Pestaña Configuración del servicio de información de ubicación

La Skype Empresarial Server 2015 Stress and Performance Tool también puede generar archivos de configuración ficticios para el Servicio de información de ubicación. Tenga en cuenta que el servicio de información de ubicación normalmente no tiene un impacto significativo en el rendimiento de los servidores. 
  
![Herramienta de aprovisionamiento de usuarios que muestra la pestaña Configuración del servicio de información de ubicación.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Si decide probar esta característica, rellene los valores del formulario y haga clic en el botón Generar archivos de configuración lis, que creará .CSV llamada:
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
Para importar estos archivos a la base de datos LIS, use estos cmdlets de PowerShell:
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Configurar perfil de usuario
<a name="BKMK_UserProfile"> </a>

Después de crear los usuarios (a través de la Herramienta de creación de usuarios), puede configurar los perfiles de usuario con la herramienta de configuración de carga Skype Empresarial Server 2015 (UserProfileGenerator.exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Ejecución de la Skype Empresarial Server configuración de carga de 2015

Inicie la herramienta Cargar configuración (UserProfileGenerator.exe) y rellene las pestañas. Esta herramienta crea un directorio para cada uno de los equipos cliente que necesitará para ejecutar las simulaciones. Cada directorio de cliente incluye un script para iniciar la Skype Empresarial Server 2015 Stress and Performance (LyncPerfTool.exe). En las secciones siguientes se proporcionan ejemplos de cómo rellenar los campos de cada pestaña de la Skype Empresarial Server de configuración de carga de 2015.
  
> [!IMPORTANT]
> Los valores específicos del usuario usados en la herramienta de configuración de carga (UserProfileGenerator.exe) deben coincidir con los valores especificados en la herramienta de creación de usuarios de Skype Empresarial Server 2015 (UserProvisioningTool.exe) del grupo de servidores. 
  
#### <a name="common-configuration-tab"></a>Ficha Configuración común

A **continuación se** muestra la pestaña Configuración común de la Herramienta de configuración de carga. Rellene los campos de la pestaña Configuración común, tal como se describe en los pasos siguientes.
  
![La pestaña Aprovisionamiento de usuarios que muestra la pestaña Configuración común.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. En el **campo Número de** máquinas disponibles, escriba el número de equipos que desea usar para ejecutar la herramienta Esfuerzo y rendimiento (LyncPerfTool.exe). Se recomienda tener un equipo por cada 4500 usuarios que va a simular, pero ese número puede variar si reduce el nivel de carga o usa solo un subconjunto de las características disponibles de la herramienta (los niveles de carga se establecen en la pestaña Escenarios generales).
    
2. En el **campo Prefijo de nombres de** usuario, escriba un prefijo para el campo nombre de usuario de todos los usuarios. Para iniciar sesión, el identificador uniforme de recursos (URI) será: *UserPrefix[User Start Index... (Número de usuarios-1)] @User domain*  , por ejemplo, myUser009@Contoso.com.
    
3. En el **campo Contraseña para todos los usuarios,** escriba la contraseña usada durante la creación de los usuarios. Si deja este campo vacío, el nombre de usuario se establecerá como contraseña.
    
4. En el **campo Índice de inicio de** usuario, escriba el índice del primer usuario que se va a configurar. Puede configurar distintos intervalos para distintos tipos o niveles de carga, pero debe ejecutar la herramienta de configuración de carga (UserProfileGenerator.exe) una vez por el rango que desee configurar.
    
5. En el **campo Número de usuarios,** escriba el número total de usuarios que va a configurar.
    
6. En el **campo Dominio de** usuario, escriba el dominio usado para el URI de SIP. Esto se usa para crear el URI sip de cada usuario para iniciar sesión en el servidor front-end de Skype Empresarial Server 2015 o en el servidor Standard Edition, y puede ser diferente del dominio de cuenta.
    
7. En el **campo Dominio de** cuenta, escriba el inicio de sesión del dominio de AD DS.
    
8. En el **campo Porcentaje de MPOP** (porcentaje de varios puntos de presencia), dé un valor para el porcentaje de usuarios que han iniciado sesión desde varios equipos o dispositivos, por ejemplo, el 10 por ciento.
    
9. Escriba el número máximo de extremos simultáneos en el campo **Iniciar sesión por segundo (por instancia).** Este es el número máximo de inicios de sesión para los usuarios y la recomendación es una tasa menor o igual a 2 por segundo (<=2).
    
10. En el **campo Fqdn** de grupo o proxy de acceso, escriba el nombre de dominio completo (FQDN) del servidor al que desea que se conecten los clientes. Si los usuarios inician sesión externamente, deberá escribir el proxy de acceso. Si los usuarios son internos, dé el FQDN de su Enterprise o Standard Edition servidor.
    
11. En el **campo Puerto,** escriba el puerto que desea que los usuarios usen para SIP (el valor predeterminado aquí es 5061).
    
12. Para el **campo Servidor de red Configuración,** dé el FQDN de grupo o proxy de acceso y, de nuevo, el **puerto**. Esta configuración solo se usa para la simulación de carga de extremos externos.
    
#### <a name="general-scenarios-tab"></a>Ficha Escenarios generales

![Herramienta de configuración de carga que muestra la pestaña Escenarios generales.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Puede configurar los niveles de carga y los parámetros para cada uno de los escenarios generales ofrecidos determinando lo que desea ejecutar o dejar deshabilitado. Estas son las opciones generales:
  
> [!NOTE]
> Los valores de nivel de carga para todos los campos, pero los Servicios de información local son **Disabled**, **Low**, **Medium**, **High** o **Custom**. Si selecciona cualquier configuración pero deshabilitada, se generarán configuraciones para cada cliente. Resultados altos en la carga máxima admitida en el servidor; medium es el 60 % de la carga alta; low es del 30 %. 
  
- **Mensajería instantánea:** Esto incluye conferencias y punto a punto; elija el valor adecuado para Nivel de carga.
    
- **Audioconferencia -** Elija un nivel de carga solo para *audioconferencia.* Las llamadas punto a punto se abordarán un poco más tarde en la sección **Escenarios de** voz. Abra la **pestaña** Avanzadas para habilitar MultiView.
    
- **Uso compartido de aplicaciones:** Elija un nivel de carga para el uso compartido de aplicaciones.
    
- **Colaboración de datos:** Elija un nivel de carga para la colaboración de datos, que incluye conferencias de datos.
    
- **Expansión de lista de distribución:** Haga clic **en el botón** Avanzadas y rellene el campo con los mismos valores configurados en la pestaña DL de la Herramienta de creación de usuarios (UserProvisioningTool.exe). Elija un nivel de carga.
    
- **Consulta web de libreta de direcciones:** Este es el servicio de búsqueda de libreta de direcciones en lugar de la descarga del archivo de libreta de direcciones. Si desea habilitar esto para las descargas de archivos de libreta de direcciones, haga clic en el **botón** Avanzadas y establezca **EnableABSDownload** en True. Dar un valor para el nivel de carga.
    
- **Servicio de grupo de respuesta -** Haga clic **en el botón** Avanzadas y especifique los URI de los grupos de respuesta que ya creó al aprovisionar Servicio de grupo de respuesta agentes. Debe elegir al menos un grupo de respuesta. Para usar más, separe los grupos de respuesta con punto y coma. Actualice **RGSUriSuffixStartIndex** y **RGSUriSuffixEndIndex a** los valores reales. Elija un nivel de carga.
    
- **Servicios de información de ubicación:** Seleccione un nivel de carga de Enabled o Disabled.
    
> [!NOTE]
> Cada uno de los escenarios tiene un botón Avanzado situado junto a él y un conjunto de casillas que habilitan variaciones a la configuración predeterminada. 
  
- Elegir  *Ad-hoc*  permitirá a la herramienta generar simulación de conferencias que se crearán durante toda la hora.
    
- Elegir  *Gran conf*  significa que se simulará un escenario de conferencia grande.
    
-  *Externo*  indica a la herramienta que también simule usuarios externos.
    
Estos botones y casillas son valores adicionales específicos de cada escenario y cambiarán el comportamiento de la Herramienta de esfuerzo y rendimiento y harán posible la personalización.
  
Para cada escenario de la ficha Escenarios generales (excepto los Servicios de información de ubicación), si el valor de Nivel de carga es **Personalizado,** la tasa de conversación se calculará con el campo correspondiente del cuadro de diálogo Avanzado. El nombre del campo puede variar, según el escenario, pero la descripción del campo se mostrará: NOTA Este número solo se usará si Custom está seleccionado en el  *menú desplegable*  .
  
Los valores **High**, **Medium** y **Low**, modificarán las tasas de conversación por modalidad en línea con el modelo de usuario que es un equilibrio de todos los escenarios. Si es necesario cambiar el nivel de carga por modalidad debido a una diferencia en el uso esperado, use una tasa de conversación personalizada.
  
#### <a name="voice-scenarios-tab"></a>Pestaña Escenarios de voz

Esta es la pestaña para la configuración de todos los escenarios relacionados con la voz.
  
![Ficha Escenarios de voz de la herramienta de configuración de carga.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Las opciones son:
  
- **VoIP -** Haga clic **en el botón** Avanzadas y agregue valores para los campos PhoneAreaCode y LocationProfile (plan de marcado). También le dará un valor para El nivel de carga. Si elige un nivel de carga para VoIP o puerta de enlace UC/RTC habilitada, se generará una red telefónica conmutada (RTC) a un archivo de configuración de comunicaciones unificadas (UC) para simular llamadas externas.
    
- **Puerta de enlace RTC/UC -** Debe elegir un valor de nivel de carga y, al elegir cualquier otra opción que no sea Deshabilitado, también tiene que proporcionar un valor para el código de área RTC haciendo clic en el **botón** Avanzadas. Haga **clic en** Agregar en el servidor de mediación y RTC. Asegúrese de que tiene una ruta configurada para el código de área.
    
    > [!TIP]
    > Puede usar el Panel de control Skype Empresarial o el Shell de administración Skype Empresarial para comprobar la configuración de la ruta de voz. 
  
- **Operador de conferencia -** Proporcione un valor para El nivel de carga. Cualquier valor distinto de Deshabilitado habilitará el **campo Número de** teléfono. Escriba el número de teléfono del Operador automático que desea usar. Haga **clic en** Avanzadas y dé un valor para el campo **LocationProfile.**
    
- **Servicio de estacionamiento de llamadas:** Aquí, proporcione un nivel de carga.
    
- **Servidor de mediación y RTC:** Cada servidor de mediación que desee usar necesita su propio simulador de RTC. Después de determinar qué cliente va a usar para el simulador, configure el servidor de mediación para enrutar las llamadas a ese equipo en el simulador rtc que configuró. Haga clic **en el botón** Agregar para configurar un valor para el servidor de mediación.
    
    > [!NOTE]
    > Cada escenario tiene un botón Avanzado situado junto a él. Los cuadros de diálogo avanzados contienen configuraciones específicas de cada escenario que cambian el comportamiento de la Herramienta de esfuerzo y rendimiento y habilitan la personalización. > Para cada escenario de la pestaña Escenarios de voz, si el valor de Nivel de carga es **Personalizado,** la tasa de conversación se calculará mediante el campo correspondiente del cuadro de diálogo Avanzado. El nombre del campo puede variar, según el escenario, pero la descripción del campo se mostrará: NOTA Este número solo se usará si Custom está seleccionado en el  *menú desplegable*  .
  
#### <a name="web-app-tab"></a>Pestaña Aplicación web

![Herramienta de configuración de carga, pestaña Aplicación web.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App admite escenarios de conferencia a través del servidor de la API web de comunicaciones unificadas (UCWA) que está instalado en un servidor front-end. Use la pestaña Aplicación web para configurar todos los escenarios relacionados con la aplicación web. Las opciones son:
  
- **General Web App Configuración -** Haga clic **en el botón Configuración** y establezca **ReachTargetServerUrl** en la IP virtual (VIP) del grupo de directorios de la VIP del grupo de servidores front-end.
    
- **Uso compartido de aplicaciones:** Seleccione un valor para Nivel de carga.
    
- **Colaboración de datos:** Seleccione un valor para Nivel de carga.
    
- **Mensajería instantánea:** Seleccione un valor para Nivel de carga.
    
- **Conferencia de voz:** Seleccione un valor para Nivel de carga.
    
> [!NOTE]
> Cada uno de los escenarios tiene un **botón** Avanzado situado junto a él. Los cuadros de diálogo avanzados contienen valores específicos de cada escenario que cambiarán el comportamiento de la Herramienta de esfuerzo y rendimiento y habilitarán customization.> Para cada uno de los escenarios de aplicación web, si el nivel de carga es **Personalizado**, se usa el valor especificado en el campo **ConversationsPerHour** en lugar del valor predeterminado.
  
#### <a name="mobility-tab"></a>Pestaña Movilidad

Use esta pestaña para configurar todos los escenarios relacionados con la movilidad.
  
![Ficha Movilidad de la herramienta de configuración de carga.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Las opciones aquí son:
  
- **General Mobility Configuración -** Haga **clic en** Configuración y establezca el campo UcwaTargetServerUrl en la DIRECCIÓN IP virtual (VIP) del grupo de directores o la VIP del grupo de servidores front-end.
    
- **Presencia y P2P Mensajería instantánea/Audio-** Seleccione un valor para Nivel de carga para habilitar la simulación de movilidad.
    
> [!NOTE]
> Cada uno de los escenarios tiene un **botón** Avanzado situado junto a él. Los cuadros de diálogo avanzados contienen valores específicos de cada escenario que cambiarán el comportamiento de la Herramienta de esfuerzo y rendimiento y habilitarán customization.> Para cada uno de los escenarios de movilidad, si el nivel de carga es **Personalizado**, se usa el valor especificado en el campo **ConversationsPerHour** en lugar del valor predeterminado.
  
#### <a name="summary-tab"></a>Ficha Resumen

La pestaña Resumen indica qué usuarios usar para cada uno de los escenarios.
  
![Ficha Resumen de la herramienta de configuración de carga.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
La pestaña Resumen indica qué usuarios usar para cada uno de los escenarios. 
  
Para configurar manualmente los intervalos de números de  usuario, active la casilla Habilitar generación de intervalos de usuarios personalizada y, a continuación, haga doble clic en el escenario de la tabla que tiene el intervalo de usuarios que desea personalizar.
  
Check **(RunClient.bat) Add sign-in delay when starting in** order to include delays in the generated batch files to correspond to the sign-in rate. Esto es útil para evitar la sobrecarga del servidor al iniciar sesión en un gran número de usuarios.
  
Haga **clic en Generar** archivos y seleccione la carpeta donde desea generar la configuración. Aparecerá un cuadro de diálogo cuando los archivos se hayan creado correctamente.
  
![Cuadro de mensaje "Cargar archivos de configuración generados correctamente". Simplemente haga clic en Aceptar.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Ejecutar LyncPerfTool
<a name="BKMK_RunTool"> </a>

Deberá crear usuarios, contactos y escenarios antes de ejecutar la herramienta de esfuerzo y rendimiento Skype Empresarial Server 2015 (LyncPerfTool.exe). Para obtener más información sobre el uso de las herramientas para realizar estas acciones, vea [Crear usuarios](using-the-tool.md#BKMK_CreateUsersAndContacts) y contactos y [Configurar](using-the-tool.md#BKMK_UserProfile) perfil de usuario anteriormente en este artículo. La ejecución de estas herramientas también generará un archivo que se ejecutará con la herramienta Esfuerzo y rendimiento como parte de un archivo por lotes con los parámetros necesarios incluidos.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Ejecución de la Skype Empresarial Server de esfuerzo y rendimiento de 2015

La herramienta Configuración de carga (UserProfileGenerator.exe) crea un archivo por lotes que permite ejecutar la herramienta De esfuerzo y rendimiento (LyncPerfTool.exe) registrando contadores de rendimiento y cargando el archivo de configuración XML. El archivo por lotes ejecuta una instancia de LyncPerfTool.exe por archivo de configuración. Para ejecutar el archivo por lotes, siga estos pasos:
  
### <a name="run-the-stress-and-performance-test"></a>Ejecutar la prueba de esfuerzo y rendimiento

1. Copie la carpeta con las carpetas de configuración y los archivos dentro en el directorio que LyncPerfTool.exe en cada equipo cliente. (Por ejemplo, si generó los archivos de configuración en la carpeta denominada 1.28_13.16.16, copie esa carpeta en la carpeta con LyncPerfTool.exe en ella. Haga esto en cada cliente).
    
2. Vaya a la carpeta de cliente y ejecute el script de lote **RunClient.** Puede hacer doble clic en el archivo por lotes en Windows Explorer y se ejecutarán todos los archivos de configuración para ese cliente. También puede ejecutar el script desde una carpeta cliente mediante la siguiente sintaxis:
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Para ejecutar la herramienta Estrés y rendimiento directamente, abra un símbolo del sistema y escriba el siguiente comando en la línea de comandos (y al hacerlo por primera vez, asegúrese de registrar los contadores de rendimiento, como se muestra en la nota más adelante en este  `regsvr32 /i /n /s LyncPerfToolPerf.dll` tema):
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Para que la herramienta muestre los valores en el archivo de configuración, incluya el parámetro en el comando anterior, de modo que  `/displayfile` tenga este aspecto:
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Para  *finalizar*  el proceso, presione Ctrl+C.
  
> [!NOTE]
> Antes de ejecutar la herramienta de esfuerzo y rendimiento directamente, debe registrar los contadores de rendimiento mediante el siguiente comando:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Cada instancia de la herramienta De esfuerzo y rendimiento que inicie empezará inmediatamente a iniciar sesión en los usuarios, normalmente a una velocidad de un usuario por segundo. 
  
La tasa máxima de inicio de sesión del usuario para el grupo es de aproximadamente 12 por segundo. Esto significa que no debe iniciar más de 12 LyncPerfTool.exe instancias al mismo tiempo mientras los usuarios siguen iniciando sesión. Un millar de usuarios tardarán unos 20 minutos en iniciar sesión por completo a una por segundo.
  
## <a name="interpreting-the-results"></a>Interpretación de los resultados
<a name="BKMK_Interpret"> </a>

La Skype Empresarial Server 2015 Stress and Performance Tool tiene muchos contadores que pueden ayudarle a comprender lo que está haciendo el cliente y si tiene problemas.
  
### <a name="client-counters"></a>Contadores de cliente

Cada instancia de LyncPerfTool.exe tiene una instancia independiente de los contadores. Cada instancia recibe el nombre de su identificador de proceso. Si los clientes están sobrecargados, pueden producirse otros problemas. Para evitar estos problemas:
  
- Supervisar el uso de cpu y memoria en los equipos cliente. Si la CPU está siempre por encima del 90 por ciento, reduzca el número de usuarios.
    
- Cuando la superficie de memoria es alta, es posible que tenga problemas si el archivo de página comienza a querse sin espacio. Compruebe que el cargo de confirmación no alcanza el límite en el equipo. Si se está ejecutando con límites de memoria, considere la posibilidad de aumentar el tamaño del archivo de página o reducir el número de usuarios.
    
Esta es una lista de contadores de rendimiento clave:
  
**Información general**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Tiempo invertido en minutos  <br/> |Tiempo invertido desde que se inició el proceso.  <br/> |
|Puntos de conexión activos  <br/> |Número de puntos de conexión conectados actualmente al servidor.  <br/> |
|Inicios de sesión con errores  <br/> |Número total de errores de inicio de sesión del punto de conexión.  <br/> |
|Intentos de inicio de sesión  <br/> |Número total de intentos de inicio de sesión de punto de conexión.  <br/> |
|Puntos de conexión desconectados  <br/> |Número total de puntos de conexión desconectados.  <br/> |
   
**Información de presencia**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|SetPresence Calls  <br/> |Número total de intentos de cambio de presencia. Para obtener distintos tipos de cambios de presencia, consulte setPresence (presence type) Calls Performance Counter.  <br/> |
|Respuestas NNN para SetPresence  <br/> |Número total de códigos de respuesta nnn recibidos desde el servidor.  <br/> |
|GetPresence Calls  <br/> |Número total de intentos de solicitud de presencia get.  <br/> |
|Respuestas NNN para GetPresence  <br/> |Número total de códigos de respuesta nnn recibidos desde el servidor.  <br/> |
   
**Información del servicio de libreta de direcciones**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|ABS Full/Delta File Downloads Attempted  <br/> |Número total de solicitudes de descarga de archivos completos o delta intentados.  <br/> |
|Descargas de archivos full/delta de ABS correctamente  <br/> |Número total de solicitudes de descarga de archivos completos o delta intentados.  <br/> |
|Contadores relacionados con el servicio de consulta web de libreta de direcciones  <br/> |Los contadores relacionados con la descarga de archivos de libreta de direcciones.  <br/> |
|Abs WS Calls attempted  <br/> |Número total de solicitudes de servicio de consulta web de libreta de direcciones intentadas.  <br/> |
|Llamadas WS de ABS correctamente  <br/> |Número total de solicitudes de servicio de consulta web de libreta de direcciones que devolvieron un código de respuesta correcto.  <br/> |
|Error en las llamadas WS de ABS  <br/> |Número total de solicitudes de servicio de consulta web de libreta de direcciones que devolvieron un código de respuesta de error.  <br/> |
   
> [!NOTE]
> Esta categoría incluye contadores usados para supervisar las descargas de archivos del servicio de libreta de direcciones (ABS) y las solicitudes de servicio de consulta web de libreta de direcciones. 
  
**Información de lista de distribución (DL)**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas intentada  <br/> |Número total de solicitudes de servicio web de expansión de listas de distribución (DLX) intentadas.  <br/> |
|Llamadas correctas  <br/> |Número total de solicitudes de servicio web DLX que devolvieron un código de respuesta correcto.  <br/> |
|Error en las llamadas  <br/> |Número total de solicitudes de servicio web DLX que devolvieron un código de respuesta de error.  <br/> |
   

  
> [!NOTE]
> Los contadores de rendimiento que se enumeran a continuación indican los números de informe de todas las llamadas de voz sobre IP (VoIP), incluidas las llamadas al servidor de mediación, al servidor de conferencia A/V, al servidor perimetral, a la aplicación de grupo de respuesta y al Operador automático de conferencia, cuando estos escenarios están habilitados. 
  
**Información básica de VoIP**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas de voz entrantes/salientes en curso actualmente.  <br/> |
|Llamadas terminadas  <br/> |Número total de llamadas de voz entrantes/salientes que ya han finalizado.  <br/> |
|Llamadas rechazadas  <br/> |Número total de llamadas de voz entrantes rechazadas.  <br/> |
|Llamadas entrantes/salientes intentada  <br/> |Número total de llamadas de voz entrantes/salientes intentada.  <br/> |
|Llamadas entrantes/salientes establecidas  <br/> |Número total de llamadas de voz entrantes/salientes establecidas.  <br/> |
|Llamadas recibidas NNN  <br/> |Número total de códigos de respuesta nnn recibidos desde el servidor.  <br/> |
|Tasa de pase VoIP (%)  <br/> |Total de llamadas establecidas/Total de llamadas intentada.  <br/> |
   
**Información de llamadas del servicio de grupo de respuesta**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas activas a la aplicación grupo de respuesta.  <br/> |
|Llamadas intentada  <br/> |Número total de llamadas intentada.  <br/> |
   
**Información de llamadas de mensajería instantánea (MI)**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas de mensajería instantánea entrantes y salientes en curso.  <br/> |
|Llamadas terminadas  <br/> |Número total de llamadas de mensajería instantánea entrantes o salientes ya finalizadas.  <br/> |
|Llamadas recibidas NNN  <br/> |Número total de códigos de respuesta nnn recibidos desde el servidor.  <br/> |
|Mensajes de mensajería instantánea recibidos/enviados  <br/> |Número total de mensajes recibidos o enviados para todas las sesiones.  <br/> |
|Llamadas entrantes/salientes intentada  <br/> |Número total de llamadas de mensajería instantánea entrantes/salientes intentada.  <br/> |
|Llamadas entrantes/salientes establecidas  <br/> |Número total de llamadas de mensajes instantáneos entrantes/salientes establecidas.  <br/> |
   
**Información de llamadas de uso compartido de aplicaciones**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas de uso compartido de aplicaciones entrantes y salientes en curso.  <br/> |
|Llamadas terminadas  <br/> |Número total de llamadas de uso compartido de aplicaciones entrantes y salientes que ya han finalizado.  <br/> |
|Llamadas recibidas NNN  <br/> |Número total de códigos de respuesta nnn recibidos desde el servidor.  <br/> |
|Llamadas entrantes/salientes intentada  <br/> |Número total de llamadas de uso compartido de aplicaciones entrantes y salientes intentada.  <br/> |
|Llamadas entrantes/salientes establecidas  <br/> |Número total de llamadas de uso compartido de aplicaciones entrantes y salientes establecidas.  <br/> |
   
**Información de llamadas caa**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas de red telefónica conmutada (RTC) entrantes o salientes en curso actualmente.  <br/> |
|Llamadas terminadas  <br/> |Número total de llamadas RTC entrantes/salientes que ya han finalizado.  <br/> |
|Llamadas entrantes/salientes intentada  <br/> |Número total de llamadas RTC entrantes/salientes intentada.  <br/> |
|Llamadas entrantes/salientes establecidas  <br/> |Número total de llamadas RTC entrantes/salientes establecidas.  <br/> |
   
**Información de conferencia**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Conferencias de mensajería instantánea activas  <br/> |Número total de conferencias de mensajería instantánea en curso.  <br/> |
|Conferencias de audio y vídeo activas  <br/> |Número total de conferencias de audio y vídeo (A/V) en curso.  <br/> |
|Conferencias de uso compartido de aplicaciones activas  <br/> |Número total de conferencias de uso compartido de aplicaciones en curso.  <br/> |
|Número de participantes  <br/> |Número total de participantes conectados actualmente a conferencias.  <br/> |
|Error de programación de conferencia  <br/> |Número total de errores al intentar programar una conferencia.  <br/> |
|Error de conferencia De unirse  <br/> |Número total de errores al intentar conectarse a una conferencia.  <br/> |
   
**Contadores de cliente ucwa**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Número total de combinaciones de IMMCU correctamente  <br/> |Número total de conferencias de mensajería instantánea unidas.  <br/> |
|Número total de combinaciones de DMCU correctamente  <br/> |Número total de conferencias A/V unidas.  <br/> |
   

