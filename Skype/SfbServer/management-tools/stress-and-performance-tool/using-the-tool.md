---
title: Using the Skype for Business Server 2015 Stress and Performance Tool
ms.author: heidip
author: microsoftheidi
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.
ms.openlocfilehash: 5f73ef6733c2f09cdf3e06bc8a6495c743d8b423
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Using the Skype for Business Server 2015 Stress and Performance Tool
 
To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.
  
There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):
  
- [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configure User Profile](using-the-tool.md#BKMK_UserProfile)
    
- [Run LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpreting the Results](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Create Users and Contacts
<a name="BKMK_CreateUsersAndContacts"> </a>

You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.
  
This is a list of helpful terms that might be useful as you read through the topics:
  
- **Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).
    
- **Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.
    
- **Distribution Lists** - Or DLs. These are objects in AD DS that contain a list of AD DS users. They're used to facilitate communications across groups of people.
    
- **Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.
    
- **U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Create Users and Contacts by using UserProvisioningTool.exe

> [!NOTE]
> Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool. You need to do this, because you're going to be creating Active Directory users. 
  
You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.
  
The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package. Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.
  
You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.
  
> [!IMPORTANT]
> When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe. You'll need to do this because the tool will be creating and configuring  *new*  AD users.
  
When the User Provisioning Tool opens, click Configuration and select the Load Configuration. 
  
To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml". This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.
  
If you have a preconfigured XML file that already contains your customized settings, you can load that file instead. Fill in the fields in the User Provisioning Tool, as described in the sections below.
  
### <a name="to-configure-server-options"></a>To configure server options:

1. In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.
    
2. In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").
    
3. In the **Password** field, type a password that will be used across all the test user accounts.
    
4. In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).
    
5. In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users. (If the OU doesn't already exist, it'll be created for you).
    
6. In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts. Make certain that the area code you chose doesn't conflict with other users' area codes in AD.
    
7. Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.
    
8. In the **Number of Users** field, give the total number of test users you want to create.
    
9. In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)
    
     ![Herramienta de aprovisionamiento de usuarios donde se muestra la ficha Creación de usuario.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Create Users button

When you click on the **Create Users** button, the input parameters you've entered are validated. If there are any validation errors, you'll be prompted to fix them. Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified). You'll see a progress bar at the bottom of the tool as it runs. Don't close the application while the progress bar is active.
  
User creation takes time, so please plan accordingly. This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.
  
If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create. Remember to use the prefix, and the suffix, along with the @sipDomain as the username. Here is an example:  *TestUser20@contoso.net*  .
  
> [!NOTE]
> If the users already exist, clicking the Create Users button will update them with any configuration changes. 
  
#### <a name="delete-users-button"></a>Delete Users button

When you click on the **Delete Users** button, the tab's input parameters will be validated. If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory. Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.
  
> [!NOTE]
> Only U.S.-formatted phone numbers are supported. Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice by default. Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls. For this reason,  *every user*  must have a *unique phone number*  .
  
> [!NOTE]
> **If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the Disable-CsUser cmdlet.**
  
> [!IMPORTANT]
> Before you create contacts, you first need to complete user replication (which is done from the Users tab). 
  
> [!IMPORTANT]
> If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database. **If the users haven't finished replicating, you'll see an error.** You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.
  
#### <a name="contacts-creation-tab"></a>Contacts Creation tab

This tab lets you give users' contacts details for your testing.
  
![Herramienta Aprovisionamiento de usuarios donde se muestra la pestaña Creación de contenido.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>To configure users' contacts, do the following:

1. In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.
    
2. Select the **Fixed** check box if you want to create an equal number of contacts for every user. If you want to vary the number of contacts created for users, clear that check box.
    
3. In the **Average Contact Groups per User** field, enter the number of contact groups per user. This number needs to be smaller than **Average Contacts per User**.
    
4. In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100. This percentage of contacts will be created with the federated users.
    
5. In the **Federated / Cross Pool User Prefix** field, give the username for federated users that will be added to the contact lists of local users.
    
6. In the **Federated / Cross Pool User SIP Domain** field, give the SIP Domain Name of the federated users.
    
7. In **User Creation** tab make sure the information is correct. Your contacts will be created from values on the User Creation tab.
    
8. Click **Create Contacts** to begin the contact creation. This process can take several minutes. After it completes, a dialog box will appear with the message, "Operation Completed Successfully." You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.
    
> [!NOTE]
> After the contacts are created, this tool will restart all the Front End Servers in the target pool. It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation. 
  
#### <a name="distribution-list"></a>Distribution List

The Skype for Business Server 2015 Stress and Performance Tool can simulate the Distribution List (DL) expansion feature in the Skype for Business 2015 client. You can skip this step if you don't intend to enable DL expansion in the User Provisioning tool.
  
![Herramienta Aprovisionamiento de usuarios donde se muestra la ficha Creación de lista de distribución.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
The Distribution List tab allows you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature. Before creating DLs, Skype for Business Server 2015 needs to be deployed, including having run ForestPrep. If this isn't done, the DL attributes will not exist in the AD schema, so the tool won't be able to create DLs.
  
### <a name="to-configure-distribution-lists"></a>To configure Distribution Lists:

1. In the **Number of Distribution Lists** field, give the total number of DLs you want to create (The recommendation here is that you start with a value that is double the number of users you have.).
    
2. In the **Distribution List Prefix** field, enter a prefix that all the DLs you create will have, for example *testDL*  . That means, at 100 DLs, your DL names will look like: testDL0, testDL1, up to testDL99.
    
3. In the **Minimum Members in a Dist. List** field, enter the minimum number of users to put in each DL.
    
4. In the **Maximum Members in a Dist. List** field, enter the maximum number of users to add in each DL.
    
#### <a name="create-distribution-lists-button"></a>Create Distribution Lists button

When you click the Create Distribution Lists button, the tool queries Active Directory to see if distribution lists matching the prefix and numbers already exist. The tool creates any DLs that don't already exist. When adding members to these newly created Distribution Lists, it'll choose the users from the range specified on the User Creation tab.
  
#### <a name="location-info-service-config-tab"></a>Location Info Service Config tab

The Skype for Business Server 2015 Stress and Performance Tool can also generate dummy configuration files for the Location Information Service. Note that the Location Information Service typically doesn't have significant performance impact on the servers. 
  
![Herramienta Aprovisionamiento de usuarios donde se muestra la pestaña Configuración del servicio de información de ubicaciones.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Si decide probar esta función, rellene los valores en el formulario y haga clic en el botón Generar archivos de configuración de LIS, que va a crear. Se llaman archivos CSV:
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
To import these files into the LIS database use these PowerShell cmdlets:
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Configure User Profile
<a name="BKMK_UserProfile"> </a>

After your users are created (via the User Creation Tool) you can configure user profiles with the Skype for Business Server 2015 Load Configuration tool (UserProfileGenerator.exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Running the Skype for Business Server 2015 Load Configuration tool

Start the Load Configuration tool (UserProfileGenerator.exe) and fill in the tabs. This tool creates a directory for each of the client computers that you'll need to run your simulations. Each client directory comes with a script to start the Skype for Business Server 2015 Stress and Performance tool (LyncPerfTool.exe). The sections below will give examples of how to fill in the fields on each tab of the Skype for Business Server 2015 Load Configuration tool.
  
> [!IMPORTANT]
> The user-specific values used in the Load Configuration tool (UserProfileGenerator.exe) must match the values specified in the Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) for the pool. 
  
#### <a name="common-configuration-tab"></a>Ficha Configuración común

The **Common Configuration** tab of the Load Configuration Tool is shown below. Fill in the fields of the Common Configuration tab, as described in the following steps.
  
![Pestaña Aprovisionamiento de usuarios donde se muestra la pestaña Configuración común.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. In the **Number of Available Machines** field, type the number of computers you want to use to run the Stress and Performance tool (LyncPerfTool.exe). We recommend that you have one computer for every 4500 users you'll be simulating, but that number may vary if you reduce the load level, or use only a subset of the tool's available features (Load levels are set on the General Scenarios tab).
    
2. In the **Prefix for User Names** field, enter a prefix for the user name field of all users. To log in the Uniform Resource Identifier (URI) will be: *UserPrefix[User Start Index…(Number Of Users-1)]@User Domain*  , for example, myUser009@Contoso.com.
    
3. In the **Password for All Users** field, enter the password used during creation of the users. If you leave this field empty the username will be set as the password.
    
4. In the **User Start Index** field, enter the index of the first user to be configured. You can configure different ranges for different types or levels of load, but you must run the Load Configuration tool (UserProfileGenerator.exe) once per the range you want to configure.
    
5. In the **Number of Users** field, enter the total number of users you're going to configure.
    
6. In the **User Domain** field, enter the domain used for the SIP URI. This is used to construct the SIP URI of each user to log on to the Skype for Business Server 2015 Front End Server or Standard Edition server, and may be different from the Account Domain.
    
7. In the **Account Domain** field, enter the AD DS domain logon.
    
8. In the **MPOP Percentage** (Multiple Point of Presence percentage) field, give a value for the percentage of users that are logged on from multiple machines or devices, for example 10 percent.
    
9. Enter the maximum number of concurrent endpoints in the **Sign in Per Second (per Instance)** field. This is the maximum number of log ins for your users, and the recommendation is a rate of less than/equal to 2 per second (<=2).
    
10. In the **Access Proxy or Pool FQDN** field, enter the fully qualified domain name (FQDN) of the server you want the clients to connect to. If the users are logging on externally, you'll need to type the access proxy. Si los usuarios son internos, asigne el FQDN de su servidor de grupo de servidores Enterprise o Standard Edition.
    
11. En el campo **puerto** , especifique el puerto que desea que los usuarios utilicen para SIP (el valor predeterminado es 5061).
    
12. For the **External Network Server Settings** field, give the Access Proxy or Pool FQDN and, again, the **Port**. These settings are used only for External endpoints load simulation.
    
#### <a name="general-scenarios-tab"></a>Ficha de casos generales

![Herramienta de configuración de carga donde se muestra la ficha Escenarios generales.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
You can configure the load levels and parameters for each of the general scenarios offered by determining what you want to run or leave disabled. Here are your general options:
  
> [!NOTE]
> Valores de nivel de carga para todos los campos excepto los servicios de información Local están **desactivado**, **bajo**, **medio**, **alto**o **personalizado**. If you select any setting but Disabled, then configurations are generated for each client. Resultados de alta en la carga máxima compatible en el servidor; medio es el 60% de la carga elevada; bajo es del 30%. 
  
- **Mensajería instantánea:** Esto incluye peer-to-peer y conferencias; elegir el valor apropiado para el nivel de carga.
    
- **Audio Conferencing -** Choose a load level for audio conferencing *only*  . Llamadas de punto a punto se abordarse más adelante en la sección **Escenarios de voz** . Abra la ficha **Opciones avanzadas** para habilitar MultiView.
    
- **Uso compartido de aplicaciones:** Elija un nivel de carga para el uso compartido de aplicaciones.
    
- **Data Collaboration -** Choose a load level for data collaboration, which includes data conferencing.
    
- **Distribution List Expansion -** Click the **Advanced** button and fill in the field with the same values configured on the DL tab of the User Creation Tool (UserProvisioningTool.exe). Elija un nivel de carga.
    
- **Consulta de Web de libreta de direcciones-** Esto es el servicio de búsqueda de la libreta de direcciones en lugar de la descarga del archivo de libreta de direcciones. If you want to enable this for address book file downloads, click the **Advanced** button and set **EnableABSDownload** to True. Proporcionar un valor para el nivel de carga.
    
- **Servicio de grupo de respuesta-** Haga clic en el botón **Opciones avanzadas** y especifique a las direcciones URI de los grupos de respuesta que ya creó cuando aprovisiona agentes de Servicio de grupo de respuesta. You must choose at least one response group. Para utilizar más, separar los grupos de respuesta con punto y coma. Actualización **RGSUriSuffixStartIndex** y **RGSUriSuffixEndIndex** a los valores reales. Elija un nivel de carga.
    
- **Servicios de información de ubicación:** Seleccione un nivel de carga de habilitado o deshabilitado.
    
> [!NOTE]
> Cada uno de los escenarios tiene un botón avanzadas que se encuentra junto a la base de datos y un conjunto de casillas de verificación que permiten variaciones en el valor predeterminado. 
  
- Elegir *Ad-hoc* permitirá la herramienta generar la simulación de conferencias que se crearán a lo largo de la hora.
    
- Si selecciona *Conf grande* significa que se simulará un gran escenario de conferencia.
    
-  *Externo* , indica a la herramienta para simular también los usuarios externos.
    
Estos botones y casillas de verificación son valores adicionales específicos para cada escenario y se cambia el comportamiento de la herramienta de rendimiento y esfuerzo y hacen posible la personalización.
  
Para cada escenario en la ficha General escenarios (excepto para los servicios de información de ubicación), si el valor del nivel de carga es **personalizada**, a continuación, la velocidad de la conversación se calculará utilizando el campo correspondiente en el cuadro de diálogo Opciones avanzadas. El nombre de campo puede diferir, dependiendo del escenario, pero indicará la descripción del campo: *Nota: este número se utilizará sólo si se selecciona personalizado en el menú desplegable* .
  
Los valores **alto**, **medio**y **bajo**, modificará los índices de conversación por modalidad en consonancia con el modelo de usuario es un equilibrio de todos los escenarios. Si hay una necesidad de cambiar el nivel de carga por modalidad debido a una diferencia en el uso esperado, utilice una velocidad de conversación personalizado.
  
#### <a name="voice-scenarios-tab"></a>Ficha de escenarios de voz

Se trata de la ficha de configuración de todos los escenarios relacionados con la voz.
  
![Herramienta de configuración de carga, ficha Escenarios de voz.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Las opciones son:
  
- **VoIP:** Haga clic en el botón **Opciones avanzadas** y agregue valores para los campos de PhoneAreaCode y LocationProfile (dial plan). También le dará un valor de nivel de carga. Si elige un nivel de carga para VoIP o UC/puerta de enlace PSTN habilitada, a continuación, una red telefónica pública conmutada (PSTN) para comunicaciones unificadas (UC) se generará el archivo de configuración para simular llamadas externas.
    
- **Puerta de enlace PSTN/UC-** Debe elegir un valor de nivel de carga, y cuando elija algo distinto deshabilitado, también tienes que proporcionar un valor para el código de área PSTN haciendo clic en el botón **Avanzadas** . Haga clic en **Agregar** en el servidor de mediación y PSTN. Asegúrese de que tiene una ruta configurada para el código de área.
    
    > [!TIP]
    > Puede utilizar ambos el Skype para el Panel de Control del negocio o Skype para el Shell de administración de negocios para verificar la configuración de ruta de voz. 
  
- **Operador de conferencia:** Proporcione un valor para el nivel de carga. Cualquier valor distinto de deshabilitado habilitará el campo de **Número de teléfono** . Escriba el número de teléfono del Operador automático que desea utilizar. Haga clic en **Avanzadas** y proporcionar un valor para el campo **LocationProfile** .
    
- **Llame al servicio de estacionamiento:** A continuación, proporcionar un nivel de carga.
    
- **Servidor de mediación y PSTN-** Cada servidor de mediación que desea usar necesita su propio simulador PSTN. Una vez que haya determinado qué cliente va a utilizar para el simulador, configuración de su servidor de mediación para enrutar llama a ese equipo en el simulador PSTN configurado. Haga clic en el botón **Agregar** para configurar un valor para el servidor de mediación.
    
    > [!NOTE]
    > Cada escenario tiene un botón avanzadas que se encuentra junto a ella. Cuadros de diálogo avanzados contienen valores específicos para cada escenario que modifican el comportamiento de la herramienta de rendimiento y esfuerzo y permiten la personalización. > Para cada escenario en la ficha de escenarios de la voz, si el valor del nivel de carga es **personalizada**, a continuación, la velocidad de la conversación se calculará utilizando el campo correspondiente en el cuadro de diálogo Opciones avanzadas. El nombre de campo puede diferir, dependiendo del escenario, pero indicará la descripción del campo: *Nota: este número se utilizará sólo si se selecciona personalizado en el menú desplegable* .
  
#### <a name="web-app-tab"></a>Ficha de la aplicación Web

![Herramienta de configuración de carga, ficha Aplicación web.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web de la aplicación admite escenarios de conferencia a través del servidor de la API de Web de comunicaciones unificadas (UCWA) que se instala en un servidor Front-End. Utilice la ficha de la aplicación Web para configurar todos los escenarios relacionados con la aplicación de web. Las opciones son:
  
- **Opciones a generales de la aplicación Web:** Haga clic en el botón **Configuración adicional** y establezca la **ReachTargetServerUrl** al grupo del directorio virtual IP (VIP) del grupo de servidores Front-End VIP.
    
- **Uso compartido de aplicaciones:** Seleccione un valor para el nivel de carga.
    
- **Colaboración de datos-** Seleccione un valor para el nivel de carga.
    
- **Mensajería instantánea:** Seleccione un valor para el nivel de carga.
    
- **Conferencias de voz-** Seleccione un valor para el nivel de carga.
    
> [!NOTE]
> Cada uno de los escenarios tiene un botón de **Opciones avanzadas** situado junto a él. Cuadros de diálogo avanzados contienen valores específicos para cada escenario que permite cambiar el comportamiento de la herramienta de rendimiento y esfuerzo personalización. > para cada uno de los escenarios de la aplicación Web, si el nivel de carga es **personalizada**, a continuación, el valor especificado en el ** ConversationsPerHour** campo se utiliza en lugar del predeterminado.
  
#### <a name="mobility-tab"></a>Ficha de movilidad

Utilice esta ficha para configurar todas las situaciones relacionadas con la movilidad.
  
![Herramienta de configuración de carga, pestaña Movilidad.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Las opciones son:
  
- **Configuración general de movilidad:** Haga clic en **Configuración adicional** y establece el campo UcwaTargetServerUrl en la IP virtual (VIP) grupo de directores o el grupo de servidores Front-End VIP.
    
- **Presencia y mensajería instantánea de P2P/Audio-** Seleccione un valor para el nivel de carga permitir la simulación de movilidad.
    
> [!NOTE]
> Cada uno de los escenarios tiene un botón de **Opciones avanzadas** situado junto a él. Cuadros de diálogo avanzados contienen valores específicos para cada escenario que permite cambiar el comportamiento de la herramienta de rendimiento y esfuerzo personalización. > para cada uno de los escenarios de movilidad, si el nivel de carga es **personalizada**, a continuación, el valor especificado en el ** ConversationsPerHour** campo se utiliza en lugar del predeterminado.
  
#### <a name="summary-tab"></a>Ficha Resumen

La ficha Resumen indica qué usuarios para cada uno de los escenarios.
  
![Herramienta de configuración de carga, ficha Resumen.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
La ficha Resumen indica qué usuarios para cada uno de los escenarios. 
  
Es posible configurar manualmente los intervalos numéricos de usuario seleccionando la casilla de verificación **Habilitar generación de rango de usuario personalizado** y, a continuación, haga doble clic en el escenario en la tabla que tiene el rango de usuario que desea personalizar.
  
Comprobar **(RunClient.bat) agregar signo de retraso al iniciar** para incluir retrasos en los archivos por lotes generado que corresponda a la velocidad de inicio de sesión. Esto es útil para evitar sobrecarga en el servidor al iniciar sesión en un gran número de usuarios.
  
Haga clic en **Generar archivos** y seleccione la carpeta donde desea generar la configuración. Cuando los archivos se han creado correctamente, aparecerá un cuadro de diálogo.
  
![Cuadro de mensaje “Archivos de configuración de carga generados correctamente”. Haga clic en Aceptar.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Ejecutar LyncPerfTool
<a name="BKMK_RunTool"> </a>

Debe crear los usuarios, contactos y escenarios antes de ejecutar el Skype para Business Server 2015 herramienta Stress and Performance (LyncPerfTool.exe). Para obtener más información acerca de cómo utilizar las herramientas para realizar estas acciones, consulte [crear usuarios y contactos](using-the-tool.md#BKMK_CreateUsersAndContacts) y [Configurar el perfil de usuario](using-the-tool.md#BKMK_UserProfile) anteriormente en este artículo. Ejecutar estas herramientas también generará un archivo que se ejecutará con los parámetros necesarios que se incluye con la herramienta de rendimiento y esfuerzo como parte de un archivo por lotes.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Ejecuta el Skype para herramientas de 2015 de Business Server Stress and Performance

La herramienta de configuración de carga (UserProfileGenerator.exe) crea un archivo por lotes que le permite ejecutar la herramienta de carga y rendimiento (LyncPerfTool.exe) mediante el registro de contadores de rendimiento y carga el archivo de configuración XML. El archivo por lotes ejecuta una instancia de LyncPerfTool.exe por el archivo de configuración. Para ejecutar el archivo por lotes siga estos pasos:
  
### <a name="run-the-stress-and-performance-test"></a>Ejecutar la prueba de esfuerzo y rendimiento

1. Copie la carpeta con los archivos dentro y carpetas de configuración al directorio que se LyncPerfTool.exe en cada equipo cliente. (Por ejemplo, si ha generado los archivos de configuración en la carpeta denominada 1.28_13.16.16, copie esa carpeta a la carpeta con LyncPerfTool.exe en él. Hacer esto en cada cliente).
    
2. Desplácese a la carpeta de cliente y ejecute la secuencia de comandos de proceso por lotes **RunClient** . Haga doble clic en el archivo por lotes en el Explorador de Windows y se ejecutará todos los archivos de configuración para ese cliente. También puede ejecutar la secuencia de comandos desde una carpeta de cliente utilizando la sintaxis siguiente:
    
  ```
  RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
  ```

Para ejecutar la herramienta de carga y rendimiento directamente, abra un símbolo del sistema y escriba el comando siguiente en la línea de comandos (y al hacerlo por primera vez, asegúrese de registrar los contadores de rendimiento `regsvr32 /i /n /s LyncPerfToolPerf.dll`, como se muestra en la nota más adelante en este tema):
  
```
LyncPerfTool.exe /file:IM_client0.xml
```

Para que la herramienta muestre los valores en el archivo de configuración, se incluyen los `/displayfile` parámetro en el comando anterior, por lo que TI tiene el siguiente aspecto:
  
```
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Al *final* del proceso, presione CTRL+c.
  
> [!NOTE]
> Antes de ejecutar la herramienta de carga y rendimiento directamente, debe registrar los contadores de rendimiento mediante el siguiente comando:`regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Cada instancia de la herramienta de rendimiento y esfuerzo que inicia comenzará inmediatamente la firma en los usuarios, normalmente a una velocidad de un usuario por segundo. 
  
El usuario inicio de sesión de velocidad máxima para el grupo es de aproximadamente 12 por segundo. Esto significa que no debe iniciar instancias de más de 12 LyncPerfTool.exe al mismo tiempo mientras los usuarios aún están firmando. Mil usuarios tardará unos 20 minutos para firmar completamente uno por segundo.
  
## <a name="interpreting-the-results"></a>Interpretar los resultados
<a name="BKMK_Interpret"> </a>

El Skype para Business Server 2015 Stress y la herramienta de rendimiento tiene muchos contadores que pueden ayudarle a comprender lo que está haciendo el cliente y, si está encontrando problemas.
  
### <a name="client-counters"></a>Contadores de cliente

Cada instancia de LyncPerfTool.exe ejecución tiene una instancia independiente de los contadores. Cada instancia se denominará por su identificador de proceso. Si los clientes están sobrecargados pueden producirse otros problemas. Para evitar estos problemas:
  
- Supervisar el uso de CPU y memoria en los equipos cliente. Si la CPU está constantemente por encima de 90%, reducir el número de usuarios.
    
- Cuando el consumo de memoria es alto, puede tener problemas si el archivo de la página comienza a quedarse sin espacio. Compruebe que la carga de transacciones no está alcanzando el límite en el equipo. Si está ejecutando en límites de memoria, considere aumentar el tamaño del archivo de paginación o reducir el número de usuarios.
    
Presentamos una lista de contadores de rendimiento clave:
  
**Información general**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Tiempo transcurrido en minutos  <br/> |Tiempo desde que se inició el proceso.  <br/> |
|Extremos activos  <br/> |Número de extremos conectados actualmente al servidor.  <br/> |
|Inicios de sesión fallidos  <br/> |Número total de errores de inicio de sesión de extremo.  <br/> |
|Intentos de inicio de sesión  <br/> |Número total de intentos de inicio de sesión de extremo.  <br/> |
|Extremos desconectados  <br/> |Número total de extremos que se han desconectado.  <br/> |
   
**Información de presencia**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas SetPresence  <br/> |Número total de presencia cambiar intentos. Para diferentes tipos de cambios de presencia, ver el contador de rendimiento de llamadas SetPresence (tipo de presencia).  <br/> |
|NNN respuestas para SetPresence  <br/> |Número total de códigos de respuesta nnn recibidos desde el servidor.  <br/> |
|Llamadas de GetPresence  <br/> |Número total de intentos de solicitud de presencia de get.  <br/> |
|NNN respuestas de GetPresence  <br/> |Número total de códigos de respuesta nnn recibidos desde el servidor.  <br/> |
   
**Información del servicio de libreta de direcciones**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Descargas de archivos ABS completo/Delta intentadas  <br/> |Número total de full o delta solicitudes de descarga de archivo ha intentado.  <br/> |
|Archivo ABS completo/Delta descarga correcta  <br/> |Número total de full o delta solicitudes de descarga de archivo ha intentado.  <br/> |
|Consulta Web de libreta de direcciones los contadores relacionados con el servicio  <br/> |Archivo de libreta de direcciones descargar contadores relacionados.  <br/> |
|ABS WS llamadas ha intentado  <br/> |Número total de solicitudes de servicio de consulta Web de libreta de direcciones ha intentado.  <br/> |
|ABS WS llamadas correctamente  <br/> |Número total de solicitudes de servicio de consulta Web de libreta de direcciones que devolvió un código de respuesta correcta.  <br/> |
|Error en las llamadas WS ABS  <br/> |Número total de solicitudes de servicio de consulta Web de libreta de direcciones que ha devuelto un código de respuesta de error.  <br/> |
   
> [!NOTE]
> Esta categoría incluye contadores para supervisar las descargas de archivos de libreta de direcciones (ABS) de servicio y las solicitudes de servicio de consulta Web de libreta de direcciones. 
  
**Información de distribución (DL) de la lista**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas ha intentado  <br/> |Número total de solicitudes de servicio de web en expansión (DLX) de distribución lista ha intentado.  <br/> |
|Llamadas se realizó correctamente  <br/> |Número total de solicitudes de servicio web DLX devolvió un código de respuesta correcta.  <br/> |
|Error en las llamadas  <br/> |Número total de solicitudes de servicio web DLX devolvió un código de respuesta de error.  <br/> |
   

  
> [!NOTE]
> Los contadores de rendimiento enumeran a continuación de números de informe para todos los voz sobre IP (VoIP) llamadas, incluidas las llamadas al servidor de mediación, A / aplicación V Conferencing Server, borde, respuesta grupo de servidores y de Operador automático de conferencia, cuando están habilitados estos escenarios. 
  
**Información básica de VoIP**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de voz entrantes/salientes llamadas continua actualmente.  <br/> |
|Termina las llamadas  <br/> |Número total de llamadas de voz entrantes/salientes ya finalizado.  <br/> |
|Llamadas rechazadas  <br/> |Número total de llamadas de voz entrantes rechazadas.  <br/> |
|Llamadas entrantes o salientes que se ha intentado  <br/> |Número total de llamadas de voz entrantes/salientes ha intentado.  <br/> |
|Llamadas entrantes o salientes establecidas  <br/> |Número total de llamadas de voz entrantes/salientes establecidas.  <br/> |
|Llamadas recibidas NNN  <br/> |Número total de códigos de respuesta nnn recibidos desde el servidor.  <br/> |
|Tasa de Pass de VoIP (%)  <br/> |Total de llamadas de llamadas de establecido/Total ha intentado.  <br/> |
   
**Información de llamadas de servicio de grupo de respuesta**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas activas para la aplicación de grupo de respuesta.  <br/> |
|Llamadas ha intentado  <br/> |Número total de llamadas ha intentado.  <br/> |
   
**Información de la llamada (IM) de mensajería instantánea**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas de mensajería instantáneas entrante y saliente continuadas.  <br/> |
|Termina las llamadas  <br/> |Número total de llamadas de mensajería instantáneas entrante y saliente ya finalizado.  <br/> |
|Llamadas recibidas NNN  <br/> |Número total de códigos de respuesta nnn recibidos desde el servidor.  <br/> |
|Mensajes Instantáneos recibidos/enviados  <br/> |Número total de mensajes recibidos o enviados para todas las sesiones.  <br/> |
|Llamadas entrantes o salientes que se ha intentado  <br/> |Número total de llamadas entrantes/salientes instantáneas mensajería llamadas ha intentado.  <br/> |
|Llamadas entrantes o salientes establecidas  <br/> |Número total de llamadas de mensajes instantáneos entrantes o salientes establecidas.  <br/> |
   
**Información de llamada de compartir aplicación**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de compartir llamadas de aplicación continuo entrantes o salientes.  <br/> |
|Termina las llamadas  <br/> |Número total de solicitud entrantes o salientes compartir llamadas ya finalizado.  <br/> |
|Llamadas recibidas NNN  <br/> |Número total de códigos de respuesta nnn recibidos desde el servidor.  <br/> |
|Llamadas entrantes o salientes que se ha intentado  <br/> |Número total de solicitud entrantes o salientes compartir llamadas ha intentado.  <br/> |
|Llamadas entrantes o salientes establecidas  <br/> |Número total de solicitud entrantes o salientes compartir llamadas establecidas.  <br/> |
   
**Información de llamada de CAA**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Llamadas activas  <br/> |Número total de llamadas entrantes/salientes de red telefónica pública conmutada (PSTN) llamadas continua actualmente.  <br/> |
|Termina las llamadas  <br/> |Número total de llamadas entrantes o salientes de PSTN ya finalizado.  <br/> |
|Llamadas entrantes o salientes que se ha intentado  <br/> |Número total de llamadas PSTN entrantes o salientes ha intentado.  <br/> |
|Llamadas entrantes o salientes establecidas  <br/> |Número total de llamadas PSTN entrantes o salientes establecidas.  <br/> |
   
**Información sobre la conferencia**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Conferencias de mensajería instantáneas activas  <br/> |Número total de curso conferencias de mensajería instantáneas.  <br/> |
|Conferencias de Audio y vídeo activas  <br/> |Número total de audio y vídeo continuo (A / V) conferencias.  <br/> |
|Aplicación activa compartir conferencias  <br/> |Número total de compartir conferencias continuada de la aplicación.  <br/> |
|Número de participantes  <br/> |Número total de participantes conectados actualmente a las conferencias.  <br/> |
|Error de programación de conferencias  <br/> |Número total de errores al intentar programar una conferencia.  <br/> |
|Unirse a conferencia error  <br/> |Número total de errores al intentar conectarse a una conferencia.  <br/> |
   
**Contadores de cliente UCWA**

|**Contador de rendimiento**|**Descripción**|
|:-----|:-----|
|Número total de IMMCU une correcta  <br/> |Número total de conferencias de mensajería instantáneas se unió.  <br/> |
|Número total de DMCU une correcta  <br/> |Número total de A / conferencias unido.  <br/> |
   

