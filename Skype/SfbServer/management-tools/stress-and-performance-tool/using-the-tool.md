---
title: Uso de la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
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
description: Para ejecutar la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015, deberá poder administrar usuarios, contactos y perfiles de usuario, configurar la herramienta para su ejecución y, a continuación, revisar los resultados o los resultados que genera la herramienta.
ms.openlocfilehash: e008a85d22753a4e649da8501bd387675bb9b536
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814950"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Uso de la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
 
Para ejecutar la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015, deberá poder administrar usuarios, contactos y perfiles de usuario, configurar la herramienta para su ejecución y, a continuación, revisar los resultados o los resultados que genera la herramienta.
  
Hay cuatro áreas implicadas en la ejecución de la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 (el archivo ejecutable es LyncPerfTool.exe):
  
- [Crear usuarios y contactos](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurar perfil de usuario](using-the-tool.md#BKMK_UserProfile)
    
- [Ejecutar LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpretar los resultados](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Crear usuarios y contactos
<a name="BKMK_CreateUsersAndContacts"> </a>

Debe usar la herramienta de aprovisionamiento de usuarios (UserProvisioningTool.exe) de Skype Empresarial Server 2015 (SB 2015) para crear usuarios y contactos para las pruebas de esfuerzo y rendimiento.
  
Esta es una lista de términos útiles que pueden resultar útiles al leer los temas:
  
- **Unidad organizativa:** unidad organizativa (OU) de Servicios de dominio de Active Directory (AD DS).
    
- **Federado o entre grupos:** usuarios que pueden comunicarse con usuarios de otros servicios de mensajería instantánea (MI).
    
- **Listas de distribución:** o DLs. Estos son objetos de AD DS que contienen una lista de usuarios de AD DS. Se usan para facilitar las comunicaciones entre grupos de personas.
    
- **Servicio** de información de ubicación: el servicio de Skype Empresarial Server 2015 que, cuando está habilitado y configurado por teléfono, permite recuperar la ubicación física para los servicios 911 mejorados (E911).
    
- **Números de** teléfono de Estados Unidos: números de teléfono asignados al usuario además del URI de SIP que se usa para enrutar llamadas entrantes y salientes en la búsqueda inversa de números (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Crear usuarios y contactos mediante UserProvisioningTool.exe

> [!NOTE]
> Antes de empezar, asegúrese de que ha iniciado sesión como miembro del grupo de seguridad Administradores de dominio para ejecutar esta herramienta. Debe hacerlo porque va a crear usuarios de Active Directory. 
  
Debe usar la Herramienta de aprovisionamiento de usuarios de Skype Empresarial Server para crear usuarios y contactos para la simulación de carga.
  
La **herramienta de aprovisionamiento** de usuarios de Skype Empresarial Server se instala con el paquete de herramienta de esfuerzo y rendimiento de Skype Empresarial **Server.** Asegúrese de que el instalador del paquete (CapacityPlanningTool.msi) se haya ejecutado en el servidor front-end o en el servidor Standard Edition que desea probar.
  
Puede iniciar la Herramienta de aprovisionamiento de usuarios de Skype Empresarial Server ejecutando el archivo UserProvisioningTool.exe (ubicado en %InstalledDirectory%LyncStressAndPerfTool\LyncStress) en el servidor front-end o en el servidor Standard Edition.
  
> [!IMPORTANT]
> Al crear un gran número de usuarios (por ejemplo, 10.000 o más), ejecute el UserProvisioningTool.exe. Tendrás que hacerlo porque la herramienta va a crear y configurar nuevos  *usuarios*  de AD.
  
Cuando se abra la Herramienta de aprovisionamiento de usuarios, haga clic en Configuración y seleccione La configuración de carga. 
  
Para empezar a configurar usuarios y contactos, cargue el archivo predeterminado incluido en el paquete, denominado "SampleData.xml". Esto rellenará previamente los campos con datos de ejemplo que deberás cambiar para que sean relevantes para la implementación.
  
Si tienes un archivo XML preconfigurado que ya contiene la configuración personalizada, puedes cargar ese archivo en su lugar. Rellene los campos de la Herramienta de aprovisionamiento de usuarios, tal como se describe en las secciones siguientes.
  
### <a name="to-configure-server-options"></a>Para configurar las opciones de servidor:

1. En el **campo FQDN** del grupo de servidores front-end, escriba el nombre de dominio completo (FQDN) del servidor Standard Edition o el grupo de servidores front-end donde desea hospedar a los usuarios.
    
2. En el **campo Prefijo de** nombre de usuario, escriba un prefijo que desee usar para ateos los nombres de usuario con fines de prueba (como "TestUser").
    
3. En el **campo Contraseña,** escriba una contraseña que se usará en todas las cuentas de usuario de prueba.
    
4. En el **campo Dominio de** cuenta, escribe el nombre de dominio de tu dominio de AD actual (el dominio en el que quieres crear los usuarios de prueba).
    
5. En el **campo Unidad organizativa,** escriba el nombre del dominio de AD donde desea crear estos usuarios de prueba. (Si la ou aún no existe, se creará automáticamente).
    
6. En el **campo Código de área** telefónica, escriba el código de área de tres dígitos que se usará en todas las cuentas de usuario de prueba. Asegúrate de que el código de área que elijas no entre en conflicto con los códigos de área de otros usuarios en AD.
    
7. Haga clic para activar la **casilla De** voz habilitada, si desea habilitar los usuarios de prueba para Telefonía IP empresarial.
    
8. En el **campo Número de usuarios,** dé el número total de usuarios de prueba que desea crear.
    
9. En  el campo Índice de inicio, asigne el número inicial que se usará como sufijo al prefijo de nombre de usuario (por ejemplo, el prefijo es "TestUser" y el nombre finalizará en "0" en el ejemplo siguiente).
    
     ![Herramienta de aprovisionamiento de usuarios que muestra la pestaña de creación de usuarios.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Botón Crear usuarios

Al hacer clic en el **botón Crear usuarios,** se validan los parámetros de entrada especificados. Si hay algún error de validación, se le pedirá que los corrija. O bien, si todos los valores son correctos, los usuarios empezarán a aparecer en AD (en la unidad organizativa que especifiques). Verás una barra de progreso en la parte inferior de la herramienta mientras se ejecuta. No cierre la aplicación mientras la barra de progreso esté activa.
  
La creación de usuarios requiere tiempo, así que planee en consecuencia. Este proceso puede tardar desde varios minutos para unos pocos usuarios hasta unas pocas horas para un gran número de usuarios.
  
Si no tienes acceso al controlador de dominio de AD en el entorno de prueba, aún puedes validar la creación de usuarios iniciando sesión como uno de los usuarios del intervalo de usuarios que especificaste crear. Recuerde usar el prefijo y el sufijo, junto con el @sipDomain como nombre de usuario. Este es un ejemplo:  <em>TestUser20@contoso.net</em>  .
  
> [!NOTE]
> Si los usuarios ya existen, al hacer clic en el botón Crear usuarios se actualizarán con los cambios de configuración. 
  
#### <a name="delete-users-button"></a>Botón Eliminar usuarios

Al hacer clic en el botón **Eliminar usuarios,** se validarán los parámetros de entrada de la pestaña. Si hay errores de validación, se le pedirá que los corrija y, si los valores de entrada son correctos, los usuarios de prueba especificados se deshabilitarán y eliminarán de Active Directory. De nuevo, aparecerá una barra de progreso en la parte inferior de esta pestaña y no debe cerrar la aplicación mientras la barra de progreso esté activa.
  
> [!NOTE]
> Solo se admiten números de teléfono con formato estadounidense. Los números de teléfono siempre se asignan a los usuarios y todos los usuarios creados por UserProvisioningTool.exe están habilitados para Telefonía IP empresarial de forma predeterminada. Cualquier escenario que use el número de teléfono, como conferencias Operador automático o llamadas UC-RTC, use este número de teléfono para enrutar correctamente las llamadas. Por este motivo, *cada usuario* debe tener un número de *teléfono único.*
  
> [!NOTE]
> **Si tiene que crear usuarios dos veces, el comando producirá un error a menos que use un código de área diferente o si los usuarios anteriores se han deshabilitado mediante el cmdlet Disable-CsUser datos.**
  
> [!IMPORTANT]
> Antes de crear contactos, primero debe completar la replicación de usuarios (que se realiza desde la pestaña Usuarios). 
  
> [!IMPORTANT]
> If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database. **Si los usuarios no han terminado de replicarse, verá un error.** You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.
  
#### <a name="contacts-creation-tab"></a>Pestaña Creación de contactos

Esta pestaña le permite proporcionar detalles de los contactos de los usuarios para las pruebas.
  
![Herramienta de aprovisionamiento de usuarios que muestra la pestaña Creación de contenidos.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Para configurar los contactos de los usuarios, haga lo siguiente:

1. En el **campo Promedio de contactos por** usuario, escriba el número promedio de contactos que se rellenarán en las listas de contactos de cada usuario.
    
2. Active la **casilla** Fijo si desea crear un número igual de contactos para cada usuario. Si desea variar el número de contactos creados para los usuarios, desactive esa casilla.
    
3. En el **campo Promedio de grupos de contactos** por usuario, escriba el número de grupos de contactos por usuario. Este número debe ser menor que **el promedio de contactos por usuario.**
    
4. En el **campo Porcentaje de contactos federados** o entre servidores, dé un número entre 0 y 100. Este porcentaje de contactos se creará con los usuarios federados.
    
5. En el **campo Prefijo** de usuario federado o entre grupos, dé el nombre de usuario para los usuarios federados que se agregarán a las listas de contactos de los usuarios locales.
    
6. En el **campo Dominio SIP de** usuario federado o entre grupos, asigne el nombre de dominio SIP de los usuarios federados.
    
7. En **la pestaña Creación** de usuarios, asegúrese de que la información es correcta. Los contactos se crearán a partir de valores en la pestaña Creación de usuarios.
    
8. Haga **clic en Crear contactos** para comenzar la creación de contactos. Este proceso puede tardar varios minutos. Cuando se complete, aparecerá un cuadro de diálogo con el mensaje "La operación se completó correctamente". Puede validar los contactos creados iniciando sesión como un usuario que se creó desde la pestaña Creación de usuarios.
    
    > [!NOTE]
    > Una vez creados los contactos, esta herramienta reiniciará todos los servidores front-end del grupo de servidores de destino. El inicio de los servidores front-end puede tardar más (hasta 2 horas), en función de cuántos contactos se crearon con esta operación. 
  
#### <a name="distribution-list"></a>Lista de distribución

La Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 puede simular la característica de expansión lista de distribución (DL) en el cliente de Skype Empresarial 2015. Puedes omitir este paso si no tienes la intención de habilitar la expansión de DL en la herramienta de aprovisionamiento de usuarios.
  
![Herramienta de aprovisionamiento de usuarios que muestra la pestaña Creación de listas de distribución.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
La pestaña Lista de distribución le permite crear listas de distribución que la Herramienta de esfuerzo y rendimiento usará para la característica Expansión de listas de distribución. Antes de crear direcciones URL, debe implementarSe Skype Empresarial Server 2015, incluida la ejecución de ForestPrep. Si esto no se hace, los atributos dl no existirán en el esquema de AD, por lo que la herramienta no podrá crear direcciones URL.
  
### <a name="to-configure-distribution-lists"></a>Para configurar listas de distribución:

1. En el **campo** Número de listas de distribución, dé el número total de DLs que desea crear (la recomendación aquí es que comience con un valor que sea el doble del número de usuarios que tiene).
    
2. En el **campo Prefijo de lista de** distribución, escriba un prefijo que tendrán todas las direcciones URL que cree, por *ejemplo, testDL*  . Esto significa que, con 100 DL, los nombres de dl tendrán el siguiente aspecto: testDL0, testDL1, hasta testDL99.
    
3. En el **campo Miembros mínimos de una lista** de distribución, escriba el número mínimo de usuarios que se colocarán en cada archivo DL.
    
4. En el **campo Máximo de miembros en una lista** de distribución, escriba el número máximo de usuarios que se agregarán a cada archivo DL.
    
#### <a name="create-distribution-lists-button"></a>Botón Crear listas de distribución

Al hacer clic en el botón Crear listas de distribución, la herramienta consulta Active Directory para ver si las listas de distribución que coinciden con el prefijo y los números ya existen. La herramienta crea cualquier DLs que aún no exista. Al agregar miembros a estas listas de distribución recién creadas, elegirá los usuarios del intervalo especificado en la pestaña Creación de usuarios.
  
#### <a name="location-info-service-config-tab"></a>Pestaña Configuración del servicio de información de ubicación

La Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 también puede generar archivos de configuración ficticios para el servicio de información de ubicación. Tenga en cuenta que el servicio de información de ubicación normalmente no tiene un impacto significativo en el rendimiento en los servidores. 
  
![Herramienta de aprovisionamiento de usuarios que muestra la pestaña Configuración del servicio de información de ubicación.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Si decide probar esta característica, rellene los valores del formulario y haga clic en el botón Generar archivos de configuración LIS, que creará . Se ha llamado a los archivos CSV:
  
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

Una vez creados los usuarios (a través de la Herramienta de creación de usuarios), puede configurar perfiles de usuario con la herramienta de configuración de carga de Skype Empresarial Server 2015 (UserProfileGenerator.exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Ejecución de la herramienta de configuración de carga de Skype Empresarial Server 2015

Inicie la herramienta de configuración de carga (UserProfileGenerator.exe) y rellene las pestañas. Esta herramienta crea un directorio para cada uno de los equipos cliente que necesitará para ejecutar las simulaciones. Cada directorio de cliente incluye un script para iniciar la herramienta Stress and Performance de Skype Empresarial Server 2015 (LyncPerfTool.exe). En las secciones siguientes se proporcionan ejemplos de cómo rellenar los campos de cada pestaña de la herramienta de configuración de carga de Skype Empresarial Server 2015.
  
> [!IMPORTANT]
> Los valores específicos del usuario usados en la herramienta de configuración de carga (UserProfileGenerator.exe) deben coincidir con los valores especificados en la Herramienta de creación de usuarios de Skype Empresarial Server 2015 (UserProvisioningTool.exe) para el grupo de servidores. 
  
#### <a name="common-configuration-tab"></a>Pestaña Configuración común

A **continuación se** muestra la pestaña Configuración común de la Herramienta de configuración de carga. Rellene los campos de la pestaña Configuración común, como se describe en los pasos siguientes.
  
![Pestaña Aprovisionamiento de usuarios que muestra la pestaña Configuración común.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. En el **campo Número de** máquinas disponibles, escribe el número de equipos que quieres usar para ejecutar la herramienta Stress and Performance (LyncPerfTool.exe). Te recomendamos que tenga un equipo por cada 4500 usuarios que simularás, pero ese número puede variar si reduces el nivel de carga o usas solo un subconjunto de las características disponibles de la herramienta (los niveles de carga se establecen en la pestaña Escenarios generales).
    
2. En el **campo Prefijo de nombres de** usuario, escriba un prefijo para el campo de nombre de usuario de todos los usuarios. Para iniciar sesión en el identificador uniforme de recursos (URI) será: *UserPrefix[User Start Index... (Número de usuarios-1)] @User dominio*  , por ejemplo, myUser009@Contoso.com.
    
3. En el **campo Contraseña para todos** los usuarios, escriba la contraseña usada durante la creación de los usuarios. Si deja este campo vacío, el nombre de usuario se establecerá como contraseña.
    
4. En el **campo Índice de inicio de** usuario, escriba el índice del primer usuario que se va a configurar. Puede configurar distintos rangos para distintos tipos o niveles de carga, pero debe ejecutar la herramienta de configuración de carga (UserProfileGenerator.exe) una vez por cada intervalo que desee configurar.
    
5. En el **campo Número de usuarios,** escriba el número total de usuarios que va a configurar.
    
6. En el **campo Dominio de** usuario, escriba el dominio usado para el URI de SIP. Esto se usa para construir el URI del SIP de cada usuario para iniciar sesión en el servidor front-end de Skype Empresarial Server 2015 o en el servidor Standard Edition, y puede ser diferente del dominio de cuenta.
    
7. En el **campo Dominio de** cuenta, escriba el inicio de sesión de dominio de AD DS.
    
8. En el **campo Porcentaje de MPOP** (porcentaje de varios puntos de presencia), da un valor para el porcentaje de usuarios que han iniciado sesión desde varios equipos o dispositivos, por ejemplo, un 10 por ciento.
    
9. Escriba el número máximo de extremos simultáneos en el campo **Iniciar sesión por segundo (por instancia).** Este es el número máximo de inicios de sesión para los usuarios y la recomendación es una tasa inferior/igual a 2 por segundo (<=2).
    
10. En el campo Proxy de acceso o **FQDN** del grupo de servidores, escriba el nombre de dominio completo (FQDN) del servidor al que desea que se conecten los clientes. Si los usuarios inician sesión externamente, deberá escribir el proxy de acceso. Si los usuarios son internos, escriba el FQDN de su servidor Enterprise Pool o Standard Edition.
    
11. En el **campo** Puerto, escriba el puerto que desea que usen los usuarios para SIP (el valor predeterminado aquí es 5061).
    
12. Para el **campo Configuración del servidor de** red externa, dé el PROXY de acceso o el FQDN del grupo de servidores y, de nuevo, el **puerto**. Esta configuración solo se usa para la simulación de carga de extremos externos.
    
#### <a name="general-scenarios-tab"></a>Pestaña Escenarios generales

![Herramienta de configuración de carga que muestra la pestaña Escenarios generales.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Puede configurar los niveles de carga y los parámetros para cada uno de los escenarios generales que se ofrecen determinando qué desea ejecutar o dejar deshabilitados. Estas son las opciones generales:
  
> [!NOTE]
> Los valores de nivel de carga de todos los campos, pero los Servicios de información local están **deshabilitados,** **bajos,** **medianos,** altos o **personalizados.**  Si selecciona cualquier opción pero deshabilitada, se generarán configuraciones para cada cliente. Resultados altos en la carga máxima admitida en el servidor; el medio es el 60 % de la carga alta; bajo es 30 %. 
  
- **Mensajería instantánea:** Esto incluye punto a punto y conferencias; elija el valor adecuado para el nivel de carga.
    
- **Audioconferencia:** Elija un nivel de carga solo para *audioconferencias.* Las llamadas punto a punto se abordarán un poco más tarde en la sección **Escenarios de** voz. Abre la **pestaña** Avanzadas para habilitar MultiView.
    
- **Uso compartido de aplicaciones:** Elija un nivel de carga para el uso compartido de aplicaciones.
    
- **Colaboración de datos:** Elija un nivel de carga para la colaboración de datos, que incluye conferencias de datos.
    
- **Expansión de lista de distribución:** Haga clic **en el botón** Avanzadas y rellene el campo con los mismos valores configurados en la pestaña DL de la Herramienta de creación de usuarios (UserProvisioningTool.exe). Elija un nivel de carga.
    
- **Consulta web de libreta de direcciones:** Este es el servicio de búsqueda de la libreta de direcciones en lugar de la descarga del archivo de libreta de direcciones. Si desea habilitar esto para las descargas  de archivos de la libreta de direcciones, haga clic en el botón Avanzadas y establezca **EnableABSDownload** en True. Dar un valor para el nivel de carga.
    
- **Servicio de grupo de respuesta-** Haga clic **en el botón** Avanzadas y especifique los URI de los grupos de respuesta que ya creó al aprovisionar Servicio de grupo de respuesta agentes. Debe elegir al menos un grupo de respuesta. Para usar más, separe los grupos de respuesta con punto y coma. Actualice **RGSUriSuffixStartIndex** y **RGSUriSuffixEndIndex a** los valores reales. Elija un nivel de carga.
    
- **Servicios de información de ubicación:** Seleccione un nivel de carga habilitado o deshabilitado.
    
> [!NOTE]
> Cada uno de los escenarios tiene un botón Avanzado junto a él y un conjunto de casillas que habilitan variaciones en la configuración predeterminada. 
  
- Si elige  *Ad-hoc,*  la herramienta podrá generar simulaciones de conferencias que se crearán a lo largo de la hora.
    
- Elegir conf  *grande*  significa que se simulará un escenario de conferencia grande.
    
-  *External*  indica a la herramienta que también simule usuarios externos.
    
Estos botones y casillas son valores adicionales específicos de cada escenario y cambiarán el comportamiento de la Herramienta de esfuerzo y rendimiento y harán posible la personalización.
  
Para cada escenario de la ficha Escenarios generales (excepto para Servicios de información de ubicación), si el valor de Nivel de carga es Personalizado **,** la frecuencia de conversación se calculará mediante el campo correspondiente en el cuadro de diálogo Avanzado. El nombre del campo puede diferir, según el escenario, pero la descripción del campo estará en estado: NOTA: Este número solo se usará si custom está seleccionado en el *menú desplegable.*
  
Los valores **High**, **Medium** y **Low** modificarán las tasas de conversación por modalidad en línea con el modelo de usuario que es un equilibrio de todos los escenarios. Si es necesario cambiar el nivel de carga por modalidad debido a una diferencia en el uso esperado, use una frecuencia de conversación personalizada.
  
#### <a name="voice-scenarios-tab"></a>Pestaña Escenarios de voz

Esta es la pestaña para la configuración de todos los escenarios relacionados con la voz.
  
![Ficha Escenarios de voz de la herramienta de configuración de carga.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Las opciones son:
  
- **VoIP:** Haga clic **en el botón** Avanzadas y agregue valores para los campos PhoneAreaCode y LocationProfile (plan de marcado). También le dará un valor para el nivel de carga. Si elige un nivel de carga para VoIP o puerta de enlace UC/RTC habilitada, se generará un archivo de configuración de red telefónica conmutada (RTC) a comunicaciones unificadas (UC) para simular llamadas externas.
    
- **Puerta de enlace RTC/UC-** Debe elegir un valor de nivel de carga y, cuando elija algo distinto de Deshabilitado, también tiene que proporcionar un valor para el código de área RTC haciendo clic en el **botón** Avanzadas. Haga **clic en Agregar** en el servidor de mediación y RTC. Asegúrese de que tiene una ruta configurada para el código de área.
    
    > [!TIP]
    > Puede usar el Panel de control de Skype Empresarial o el Shell de administración de Skype Empresarial para comprobar la configuración de la ruta de voz. 
  
- **Operador de conferencia -** Proporcione un valor para el nivel de carga. Cualquier valor que no sea Deshabilitado habilitará el **campo Número de** teléfono. Escriba el número de teléfono del Operador automático que desea usar. Haga **clic en** Avanzadas y dé un valor para el campo **LocationProfile.**
    
- **Servicio de estacionamiento de llamadas:** Aquí, proporcione un nivel de carga.
    
- **Servidor de mediación y RTC:** Cada servidor de mediación que desee usar necesita su propio simulador de RTC. Después de determinar qué cliente va a usar para el simulador, configure el servidor de mediación para enrutar las llamadas a ese equipo en el simulador de RTC que configuró. Haga clic **en el botón** Agregar para configurar un valor para el servidor de mediación.
    
    > [!NOTE]
    > Cada escenario tiene un botón Avanzado junto a él. Los cuadros de diálogo avanzados contienen configuraciones específicas para cada escenario que cambian el comportamiento de la Herramienta de esfuerzo y rendimiento y habilitan la personalización. > Para cada escenario de la ficha Escenarios de voz, si el valor de Nivel de carga es **Personalizado,** la frecuencia de conversación se calculará mediante el campo correspondiente en el cuadro de diálogo Avanzado. El nombre del campo puede diferir, según el escenario, pero la descripción del campo estará en estado: NOTA: Este número solo se usará si custom está seleccionado en el *menú desplegable.*
  
#### <a name="web-app-tab"></a>Pestaña Aplicación web

![Herramienta de configuración de carga, pestaña aplicación web.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App admite escenarios de conferencia a través del servidor de la API web de comunicaciones unificadas (UCWA) instalado en un servidor front-end. Use la pestaña Aplicación web para configurar todos los escenarios relacionados con la aplicación web. Las opciones son:
  
- **Configuración general de la aplicación web:** Haga clic **en el botón Configuración** adicional y establezca **ReachTargetServerUrl** en la DIRECCIÓN IP virtual (VIP) del grupo de directorios de la DIRECCIÓN VIP del grupo de servidores front-end.
    
- **Uso compartido de aplicaciones:** Seleccione un valor para el nivel de carga.
    
- **Colaboración de datos:** Seleccione un valor para el nivel de carga.
    
- **Mensajería instantánea:** Seleccione un valor para el nivel de carga.
    
- **Conferencia de voz:** Seleccione un valor para el nivel de carga.
    
> [!NOTE]
> Cada uno de los escenarios tiene un **botón** Avanzado junto a él. Los cuadros de diálogo avanzados contienen valores específicos de cada escenario que cambiarán el comportamiento de la herramienta Stress and Performance y habilitarán la personalización.> Para cada uno de los escenarios de Web App, si el nivel de carga es **Personalizado**, se usa el valor especificado en el campo **ConversationsPerHour** en lugar del valor predeterminado.
  
#### <a name="mobility-tab"></a>Pestaña Movilidad

Use esta pestaña para configurar todos los escenarios relacionados con la movilidad.
  
![Pestaña Movilidad de la herramienta de configuración de carga.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Las opciones aquí son:
  
- **Configuración de movilidad general:** Haga **clic en Configuración** adicional y establezca el campo UcwaTargetServerUrl en la DIRECCIÓN IP virtual (VIP) del grupo de directores o la VIP del grupo de servidores front-end.
    
- **Presencia y mensajería instantánea/audio P2P:** Seleccione un valor para el nivel de carga para habilitar la simulación de movilidad.
    
> [!NOTE]
> Cada uno de los escenarios tiene un **botón** Avanzado junto a él. Los cuadros de diálogo avanzados contienen valores específicos de cada escenario que cambiarán el comportamiento de la Herramienta de esfuerzo y rendimiento y habilitarán la personalización.> Para cada uno de los escenarios de movilidad, si el nivel de carga es Personalizado **,** se usa el valor especificado en el campo **ConversationsPerHour** en lugar del valor predeterminado.
  
#### <a name="summary-tab"></a>Pestaña Resumen

La pestaña Resumen indica qué usuarios usar para cada uno de los escenarios.
  
![Ficha Resumen de la herramienta de configuración de carga.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
La pestaña Resumen indica qué usuarios usar para cada uno de los escenarios. 
  
Es posible configurar manualmente los intervalos de números  de usuario activando la casilla Habilitar generación de intervalos de usuarios personalizados y, a continuación, haciendo doble clic en el escenario de la tabla que tiene el intervalo de usuarios que desea personalizar.
  
Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate. Esto es útil para evitar la sobrecarga del servidor al iniciar sesión en un gran número de usuarios.
  
Haz **clic en Generar** archivos y selecciona la carpeta donde quieres generar la configuración. Aparecerá un cuadro de diálogo cuando los archivos se hayan creado correctamente.
  
![Cuadro de mensaje "Cargar archivos de configuración generados correctamente". Simplemente haga clic en Aceptar.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Ejecutar LyncPerfTool
<a name="BKMK_RunTool"> </a>

Deberá crear usuarios, contactos y escenarios antes de ejecutar la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 (LyncPerfTool.exe). Para obtener más información sobre cómo usar las herramientas para realizar estas acciones, consulte [Crear](using-the-tool.md#BKMK_CreateUsersAndContacts) usuarios y contactos y [Configurar](using-the-tool.md#BKMK_UserProfile) perfil de usuario anteriormente en este artículo. Ejecutar estas herramientas también generará un archivo que se ejecutará con la herramienta Stress and Performance como parte de un archivo por lotes con los parámetros necesarios incluidos.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Ejecución de la herramienta stress and performance de Skype Empresarial Server 2015

La herramienta de configuración de carga (UserProfileGenerator.exe) crea un archivo por lotes que permite ejecutar la herramienta Stress and Performance (LyncPerfTool.exe) registrando contadores de rendimiento y cargando el archivo de configuración XML. El archivo por lotes ejecuta una instancia de LyncPerfTool.exe por archivo de configuración. Para ejecutar el archivo por lotes, siga estos pasos:
  
### <a name="run-the-stress-and-performance-test"></a>Ejecutar la prueba de esfuerzo y rendimiento

1. Copie la carpeta con las carpetas de configuración y los archivos dentro del directorio que LyncPerfTool.exe en cada equipo cliente. (Por ejemplo, si generó los archivos de configuración en la carpeta denominada 1.28_13.16.16, copie esa carpeta en la carpeta con LyncPerfTool.exe en ella. Haga esto en cada cliente).
    
2. Navegue a la carpeta de cliente y ejecute el script de lote **RunClient.** Puedes hacer doble clic en el archivo por lotes en el Explorador de Windows y se ejecutarán todos los archivos de configuración para ese cliente. También puede ejecutar el script desde una carpeta de cliente mediante la siguiente sintaxis:
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Para ejecutar la herramienta Stress and Performance directamente, abra un símbolo del sistema y escriba el siguiente comando en la línea de comandos (y al hacerlo por primera vez, asegúrese de registrar los contadores de rendimiento, como se muestra en la nota más adelante en este  `regsvr32 /i /n /s LyncPerfToolPerf.dll` tema):
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Para que la herramienta muestre los valores en el archivo de configuración, incluya el parámetro en el comando anterior para que  `/displayfile` tenga este aspecto:
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Para  *finalizar*  el proceso, presione Ctrl + C.
  
> [!NOTE]
> Antes de ejecutar la herramienta Stress and Performance directamente, debe registrar los contadores de rendimiento mediante el siguiente comando:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Todas las instancias de la herramienta Stress and Performance que inicies comenzarán inmediatamente a iniciar sesión en los usuarios, normalmente a una velocidad de un usuario por segundo. 
  
La tasa máxima de inicio de sesión de usuario para el grupo es de aproximadamente 12 por segundo. Esto significa que no debe iniciar más de 12 instancias de LyncPerfTool.exe al mismo tiempo mientras los usuarios siguen iniciando sesión. 1.000 usuarios tardarán unos 20 minutos en iniciar sesión por completo a la vez.
  
## <a name="interpreting-the-results"></a>Interpretar los resultados
<a name="BKMK_Interpret"> </a>

La Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 tiene muchos contadores que pueden ayudarle a comprender lo que está haciendo el cliente y si tiene problemas.
  
### <a name="client-counters"></a>Contadores de cliente

Cada instancia de LyncPerfTool.exe en ejecución tiene una instancia independiente de los contadores. Cada instancia recibe el nombre de su identificador de proceso. Si los clientes están sobrecargados, pueden producirse otros problemas. Para evitar estos problemas:
  
- Supervise el uso de cpu y memoria en los equipos cliente. Si la CPU está siempre por encima del 90 por ciento, reduzca el número de usuarios.
    
- Cuando la superficie de memoria es alta, puede encontrarse con problemas si el archivo de página comienza a querse sin espacio. Comprueba que la confirmación de cargo no alcanza el límite en el equipo. Si se encuentra con límites de memoria, considere la posibilidad de aumentar el tamaño del archivo de página o reducir el número de usuarios.
    
Esta es una lista de contadores clave de rendimiento:
  
**Información general**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Tiempo invertido en minutos  <br/> |Tiempo empleado desde que se inició el proceso.  <br/> |
|Puntos de conexión activos  <br/> |Número de extremos actualmente conectados al servidor.  <br/> |
|Inicios de sesión con errores  <br/> |Número total de errores de inicio de sesión en el punto de conexión.  <br/> |
|Intentos de inicio de sesión  <br/> |Número total de intentos de inicio de sesión de punto de conexión.  <br/> |
|Puntos de conexión desconectados  <br/> |Número total de puntos de conexión que se han desconectado.  <br/> |
   
**Información de presencia**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas SetPresence  <br/> |Número total de intentos de cambio de presencia. Para obtener distintos tipos de cambios de presencia, consulte el contador de rendimiento de llamadas setPresence (tipo de presencia).  <br/> |
|Respuestas NNN para SetPresence  <br/> |Número total de códigos de respuesta n recibidos del servidor.  <br/> |
|Llamadas GetPresence  <br/> |Número total de intentos de solicitud de presencia.  <br/> |
|Respuestas NNN para GetPresence  <br/> |Número total de códigos de respuesta n recibidos del servidor.  <br/> |
   
**Información del servicio de libreta de direcciones**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|ABS Full/Delta File Downloads Attempted  <br/> |Número total de solicitudes de descarga de archivos completos o delta que se han intentado.  <br/> |
|Descargas de archivos completos/delta de ABS correctamente  <br/> |Número total de solicitudes de descarga de archivos completos o delta que se han intentado.  <br/> |
|Contadores relacionados con el servicio de consulta web de libreta de direcciones  <br/> |Los contadores relacionados se descargan en el archivo de la libreta de direcciones.  <br/> |
|Abs WS Calls attempted  <br/> |Número total de solicitudes de servicio de consulta web de libreta de direcciones intentadas.  <br/> |
|Llamadas WS de ABS correctas  <br/> |Número total de solicitudes de servicio de consulta web de libreta de direcciones que devolvieron un código de respuesta correcto.  <br/> |
|Error en las llamadas WS de ABS  <br/> |Número total de solicitudes de servicio de consulta web de libreta de direcciones que devolvieron un código de respuesta de error.  <br/> |
   
> [!NOTE]
> Esta categoría incluye contadores que se usan para supervisar las descargas de archivos del servicio de libreta de direcciones (ABS) y las solicitudes del servicio de consulta web de libreta de direcciones. 
  
**Información de lista de distribución (DL)**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas intentada  <br/> |Número total de solicitudes de servicio web de expansión de listas de distribución (DLX) intentadas.  <br/> |
|Llamadas correctas  <br/> |Número total de solicitudes de servicio web DLX que devolvieron un código de respuesta correcto.  <br/> |
|Llamadas con errores  <br/> |Número total de solicitudes de servicio web DLX que devolvieron un código de respuesta de error.  <br/> |
   

  
> [!NOTE]
> Los contadores de rendimiento que se enumeran a continuación informan de los números de todas las llamadas de voz sobre IP (VoIP), incluidas las llamadas al servidor de mediación, al servidor de conferencia A/V, al servidor perimetral, a la aplicación grupo de respuesta y al Operador automático de conferencia, cuando estos escenarios están habilitados. 
  
**Información básica de VoIP**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas de voz entrantes/salientes en curso actualmente.  <br/> |
|Llamadas finalizadas  <br/> |Número total de llamadas de voz entrantes y salientes que ya han finalizado.  <br/> |
|Llamadas rechazadas  <br/> |Número total de llamadas de voz entrantes rechazadas.  <br/> |
|Llamadas entrantes/salientes intentada  <br/> |Número total de llamadas de voz entrantes/salientes intentada.  <br/> |
|Llamadas entrantes/salientes establecidas  <br/> |Número total de llamadas de voz entrantes/salientes establecidas.  <br/> |
|NNN de llamadas recibidas  <br/> |Número total de códigos de respuesta n recibidos del servidor.  <br/> |
|Velocidad de paso voIP (%)  <br/> |Total de llamadas establecidas/Total de llamadas intentada.  <br/> |
   
**Información de llamada del servicio de grupo de respuesta**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas activas a la aplicación Grupo de respuesta.  <br/> |
|Llamadas intentada  <br/> |Número total de llamadas intentada.  <br/> |
   
**Información de llamadas de mensajería instantánea (MI)**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas de mensajería instantánea entrantes o salientes en curso.  <br/> |
|Llamadas finalizadas  <br/> |Número total de llamadas de mensajería instantánea entrantes o salientes que ya han finalizado.  <br/> |
|NNN de llamadas recibidas  <br/> |Número total de códigos de respuesta n recibidos del servidor.  <br/> |
|Mensajes de mensajería instantánea recibidos/enviados  <br/> |Número total de mensajes recibidos o enviados para todas las sesiones.  <br/> |
|Llamadas entrantes/salientes intentada  <br/> |Número total de llamadas entrantes y salientes de mensajería instantánea intentada.  <br/> |
|Llamadas entrantes/salientes establecidas  <br/> |Número total de llamadas de mensajes instantáneos entrantes/salientes establecidas.  <br/> |
   
**Información de llamadas de uso compartido de aplicaciones**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas entrantes y salientes de uso compartido de aplicaciones en curso.  <br/> |
|Llamadas finalizadas  <br/> |Número total de llamadas de uso compartido de aplicaciones entrantes y salientes que ya han finalizado.  <br/> |
|NNN de llamadas recibidas  <br/> |Número total de códigos de respuesta n recibidos del servidor.  <br/> |
|Llamadas entrantes/salientes intentada  <br/> |Número total de llamadas de uso compartido de aplicaciones entrantes y salientes intentada.  <br/> |
|Llamadas entrantes/salientes establecidas  <br/> |Número total de llamadas de uso compartido de aplicaciones entrantes y salientes establecidas.  <br/> |
   
**Información de llamadas de CAA**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas entrantes y salientes de la red telefónica conmutada (RTC) actualmente en curso.  <br/> |
|Llamadas finalizadas  <br/> |Número total de llamadas RTC entrantes/salientes que ya han finalizado.  <br/> |
|Llamadas entrantes/salientes intentada  <br/> |Número total de llamadas RTC entrantes/salientes intentada.  <br/> |
|Llamadas entrantes/salientes establecidas  <br/> |Número total de llamadas RTC entrantes/salientes establecidas.  <br/> |
   
**Información de conferencia**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Conferencias de mensajería instantánea activas  <br/> |Número total de conferencias de mensajería instantánea en curso.  <br/> |
|Conferencias de audio y vídeo activas  <br/> |Número total de conferencias de audio y vídeo (A/V) en curso.  <br/> |
|Conferencias de uso compartido de aplicaciones activas  <br/> |Número total de conferencias de uso compartido de aplicaciones en curso.  <br/> |
|Número de participantes  <br/> |Número total de participantes actualmente conectados a conferencias.  <br/> |
|Error de programación de conferencia  <br/> |Número total de errores al intentar programar una conferencia.  <br/> |
|Error de unirse a la conferencia  <br/> |Número total de errores al intentar conectarse a una conferencia.  <br/> |
   
**Contadores de cliente de UCWA**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Número total de combinaciones de IMMCU correctas  <br/> |Número total de conferencias de mensajería instantánea unidas.  <br/> |
|Número total de combinaciones de DMCU correctas  <br/> |Número total de conferencias A/V unidas.  <br/> |
   

