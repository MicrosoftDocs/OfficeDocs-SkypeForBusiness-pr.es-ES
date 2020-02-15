---
title: Configurar el perfil de usuario
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 842a5ade3e0484d0b084f48ac75a2b13984706e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a>Configurar el perfil de usuario

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2018-10-11_

Las herramientas incluidas en el paquete de la herramienta de esfuerzo y rendimiento de Lync Server 2013 permiten crear y configurar cuentas de usuario de prueba que puede usar para ejecutar simulaciones de carga. Use la herramienta de creación de usuarios de Lync Server 2013 para crear los usuarios. (Para obtener más información, consulte [Create Users and Contacts](create-users-and-contacts.md)). Una vez creados los usuarios, configure los perfiles de usuario con la herramienta de configuración de carga de Lync Server 2013.

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a>Ejecución de la herramienta de configuración de carga de Lync Server 2013

Para configurar los perfiles de usuario, ejecute la herramienta de configuración de carga de Lync Server 2013 (UserProfileGenerator. exe) y rellene cada una de las pestañas. UserProfileGenerator. exe genera un directorio para cada uno de los equipos cliente que necesita para ejecutar la simulación. Cada directorio de cliente también incluye un script para iniciar todas las instancias de la herramienta stress and performance de Lync Server 2013 (LyncPerfTool. exe).

<div>


> [!IMPORTANT]  
> Los valores específicos del usuario especificados en UserProfileGenerator deben coincidir con los valores especificados en la herramienta de creación de usuarios de Lync Server 2013 (UserProvisioningTool) para el grupo de servidores.



</div>

Rellene los campos de cada ficha de la herramienta de configuración de carga de Lync Server 2013, tal y como se describe en las secciones siguientes.

<div>

## <a name="common-configuration"></a>Configuración común

La ficha **configuración común** de la herramienta de configuración de carga de Lync Server 2013 se muestra en la figura siguiente. Rellene los campos de la ficha **configuración común** , tal y como se describe en los siguientes pasos.

![Ficha Configuración común.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Ficha Configuración común.")

1.  En **número de equipos disponibles**, escriba o haga clic en el número de equipos que desea usar para ejecutar LyncPerfTool. exe. Le recomendamos que tenga un equipo por cada 4.500 usuarios que vaya a simular. Ese número puede variar si se reduce el nivel de carga o si solo se usa un subconjunto de las características disponibles. (Los niveles de carga se establecen en la ficha **escenarios generales** ).

2.  En **prefijo para los nombres de usuario**, escriba el prefijo del nombre de usuario de los usuarios. Para iniciar sesión, el identificador uniforme de recursos (URI) será: UserPrefix\[índice de inicio de usuario... (Número de usuarios: 1) \]@User dominio.

3.  En **contraseña para todos los usuarios**, escriba la contraseña que se usó para crear los usuarios. Si deja este campo en blanco, el nombre de usuario se usará como la contraseña.

4.  En **Índice de inicio de usuario**, haga clic o escriba el índice del primer usuario que se va a configurar. Puede configurar diferentes rangos para distintos tipos o niveles de carga, pero debe ejecutar UserProfileGenerator. exe una vez por el intervalo que desea configurar.

5.  En **número de usuarios**, haga clic o escriba el número total de usuarios que va a configurar.

6.  En **dominio de usuario**, escriba el dominio que se usará para el URI del SIP. Se usa para construir el URI de SIP de cada usuario para iniciar sesión en el servidor front-end de Lync Server 2013 o el servidor Standard Edition. Puede ser diferente del dominio de la cuenta.

7.  En **dominio de cuenta**, escriba el inicio de sesión de dominio de servicios de dominio de Active Directory.

8.  Escriba el número máximo de puntos de conexión simultáneos en el **Inicio de sesión por segundo (por instancia)** para los que desea que la herramienta inicie sesión en todos los extremos o usuarios. La frecuencia recomendada es \<= 2 por segundo/el SKU estándar fe.

9.  En **proxy de acceso o FQDN del grupo**de servidores, escriba el nombre de dominio completo (FQDN) del servidor al que desea que se conecten los clientes. Si los usuarios inician sesión externamente, especifique el proxy de acceso. Si los usuarios son internos, especifique el FQDN de su grupo de servidores o servidor Standard Edition.

10. En **Puerto**, haga clic o escriba el puerto que desea que usen los usuarios para SIP (el valor predeterminado es 5061).

Para la configuración del servidor de red externo, especifique el **proxy de acceso o el FQDN del grupo** de servidores y el **Puerto**. Esta configuración se usa únicamente para la simulación de carga de extremos externos.

</div>

<div>

## <a name="general-scenarios"></a>Escenarios generales

La ficha **escenarios generales** de la herramienta de configuración de carga de Lync Server 2013 se muestra en la figura siguiente.

Configure los niveles de carga y los parámetros para cada uno de los escenarios generales que desee ejecutar o deje deshabilitado.

![Ficha escenarios generales.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Ficha escenarios generales.")

1.  En la **mensajería instantánea**, que incluye punto a punto y Conferencia, especifique el valor adecuado para el nivel de carga.
    
    <div>
    

    > [!NOTE]  
    > Los valores de nivel de carga para todos los campos (excepto servicios de información de ubicación) están <STRONG>deshabilitados</STRONG>, <STRONG>bajo</STRONG>, <STRONG>medio</STRONG>, <STRONG>alto</STRONG>y <STRONG>personalizado</STRONG>. Cuando se selecciona Low, Medium, High o Custom, se generarán configuraciones para cada modalidad y cliente. High dará como resultado que la carga máxima admitida se genere para el servidor, Medium corresponde al 60 por ciento de la carga y Low equivale al 30 por ciento de la carga.

    
    </div>

2.  En audioconferencia, que solo es **audioconferencia, especifique**el valor adecuado para el nivel de carga. Las llamadas punto a punto se tratan en la sección escenarios de voz más adelante en este tema. Para habilitar la multivista, abra la pestaña **avanzadas** de esa modalidad.

3.  En **uso compartido de aplicaciones**, especifique el valor adecuado para el nivel de carga.

4.  En la **colaboración de datos**, que incluye la Conferencia de datos, especifique el valor adecuado para el nivel de carga.

5.  En **expansión**de la lista de distribución, especifique el valor adecuado para el nivel de carga. También debe hacer clic en el botón **avanzadas** y, a continuación, rellenar los campos con los mismos valores que ha configurado en la ficha **lista de distribución** de la herramienta de creación de usuarios de Lync Server (UserProvisioningTool. exe). Para obtener más información sobre estos campos, consulte [crear usuarios y contactos](create-users-and-contacts.md) .

6.  En **consulta Web**de la libreta de direcciones, que es el servicio de búsqueda de la libreta de direcciones (no la descarga del archivo de la libreta de direcciones), especifique el valor adecuado para el nivel de carga. Para habilitar la descarga de la libreta de direcciones, haga clic en el botón **Opciones avanzadas** correspondiente y, a continuación, establezca **EnableABSDownload** en true.

7.  En **servicio de grupo de respuesta**, especifique el valor adecuado para el nivel de carga. También debe hacer clic en el botón **Opciones avanzadas** correspondiente y, a continuación, especificar los URI de los grupos de respuesta que ya ha creado al aprovisionar agentes del servicio del grupo de respuesta. Debe especificar al menos un grupo de respuesta. Use punto y coma para separar varios grupos de respuesta. Actualice RGSUriSuffixStartIndex y RGSUriSuffixEndIndex a los valores reales.

8.  En **servicios de información de ubicación**, seleccione el valor adecuado para el nivel de carga. El nivel de carga para los servicios de información de ubicación debe estar **habilitado** o **deshabilitado**.

<div>


> [!NOTE]  
> Cada uno de los escenarios tiene un botón <STRONG>avanzado</STRONG> situado junto a él y un conjunto de casillas de verificación que habilitan variaciones de los escenarios. <STRONG>Ad-hoc</STRONG> significa generar una simulación de conferencias que se crearán a lo largo de la hora. <STRONG>Conf de gran tamaño</STRONG> significa que se simulará un escenario de conferencia de gran tamaño. <STRONG>External</STRONG> significa también simular usuarios externos.<BR>Estos botones y casillas de verificación permiten el acceso a valores específicos de cada escenario que cambiarán el comportamiento de la herramienta stress and performance de Lync Server 2013 (LyncPerfTool) y facilitarán la personalización. Para cada escenario de la ficha <STRONG>escenarios generales</STRONG> (excepto para servicios de información de ubicación), si el valor de nivel de carga es <STRONG>personalizado</STRONG>, la tasa de conversaciones se calculará usando el campo correspondiente en el cuadro de diálogo <STRONG>Opciones avanzadas</STRONG> . El nombre del campo difiere en función del escenario, pero la descripción del campo será "Nota: este número solo se usará si se selecciona personalizado en el menú desplegable". En general, los valores <STRONG>alto</STRONG>, <STRONG>medio</STRONG>y <STRONG>bajo</STRONG> modificarán las tasas de conversación por modalidad en línea con el modelo de usuario que es un equilibrio de todos los escenarios. Si es necesario cambiar el nivel de carga por modalidad debido a una diferencia en el uso esperado, se recomienda usar una tasa de conversación <STRONG>personalizada</STRONG> .<BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a>Escenarios de voz

La ficha **escenarios de voz** de la herramienta de configuración de carga de Lync Server 2013 se muestra en la figura siguiente.

Use la pestaña **escenarios de voz** para configurar todos los escenarios relacionados con la voz.

![Ficha escenarios de voz.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Ficha escenarios de voz.")

1.  En **VoIP**, haga clic en el botón **avanzadas** y, a continuación, proporcione valores para los campos **PhoneAreaCode** y **LocationProfile** (plan de marcado). También debe especificar un valor para el **nivel de carga**. Si se habilita el nivel de carga de **VoIP** y la **puerta de enlace RTC/RTC** , siempre se generará un archivo de configuración de red telefónica conmutada (RTC) en el archivo de configuración de comunicaciones unificadas (UC) que simulará las llamadas externas.

2.  En **puerta de enlace de comunicaciones unificadas/RTC**, especifique un valor para el nivel de carga. Si selecciona un nivel de carga que no sea **deshabilitado**, debe proporcionar un valor para el **código de área RTC** haciendo clic en el botón **Agregar** en servidor de mediación y RTC. Compruebe que tiene una ruta configurada para ese código de área.
    
    <div>
    

    > [!NOTE]  
    > Puede usar el panel de control de Lync Server o el shell de administración de Lync Server para comprobar la configuración de la ruta de voz.

    
    </div>

3.  En el **operador de conferencia**, especifique un valor para el nivel de carga. Al seleccionar un nivel de carga (distinto de **deshabilitado**), se habilitará el campo **número de teléfono** . Escriba el número de teléfono del operador automático que desea usar. Además, haga clic en el botón **avanzadas** y, a continuación, especifique un valor para el campo **LocationProfile** .

4.  En **servicio de estacionamiento de llamadas**, especifique el valor adecuado para el **nivel de carga**.

5.  En el **servidor de mediación y**en la RTC, para cada servidor de mediación que desee usar, debe tener un simulador de RTC independiente. Una vez que haya determinado el cliente que va a usar como simulador, debe configurar el servidor de mediación para enrutar las llamadas a ese equipo en el puerto del simulador RTC que configuró. Haga clic en **Agregar** para configurar el valor para el servidor de mediación.

<div>


> [!NOTE]  
> Cada uno de los escenarios tiene un botón <STRONG>avanzado</STRONG> situado junto a él. Estos botones permiten el acceso a valores específicos de cada escenario que cambiarán el comportamiento de la herramienta stress and performance de Lync Server 2013 (LyncPerfTool) y habilitación de la personalización. Para cada escenario de la <STRONG>pestaña escenarios de voz</STRONG> , si el valor de nivel de <STRONG>carga</STRONG> es <STRONG>personalizado</STRONG>, la tasa de conversaciones se calculará usando el campo correspondiente en el cuadro de diálogo <STRONG>Opciones avanzadas</STRONG> . El nombre del campo difiere en función del escenario, pero la descripción del campo será "Nota: este número solo se usará si se selecciona personalizado en el menú desplegable".



</div>

</div>

<div>

## <a name="reach"></a>Acceder

REACH es una nueva experiencia en Lync Server 2013 que admite escenarios de conferencia a través del servidor de API Web de comunicaciones unificadas (UCWA) instalado en el servidor front-end. En la siguiente figura se muestra la ficha **alcance** de la herramienta de configuración de carga de Lync Server 2013.

Use la ficha **alcance** para configurar todos los escenarios relacionados con el alcance.

![Ficha alcance.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Ficha alcance.")

1.  Haga clic en el botón **avanzadas** junto a **Configuración general de alcance**. Establezca el campo **UcwaTargetServerUrl** en la dirección IP virtual (VIP) del grupo de directores o en la VIP del grupo de servidores front-end.

2.  En **uso compartido de aplicaciones**, **colaboración de datos**y **mensajería instantánea**, seleccione el valor adecuado para el **nivel de carga**.

<div>


> [!NOTE]  
> Cada uno de los escenarios tiene un botón <STRONG>avanzado</STRONG> situado junto a él. Estos botones permiten el acceso a valores específicos de cada escenario que cambiarán el comportamiento de la herramienta stress and performance de Lync Server 2013 (LyncPerfTool) y habilitación de la personalización. Para cada uno de los escenarios de Reach, si el <STRONG>nivel de carga</STRONG> es <STRONG>personalizado</STRONG>, se usa el valor especificado en el campo <STRONG>ConversationsPerHour</STRONG> en lugar del predeterminado



</div>

Use la ficha **movilidad** para configurar todos los escenarios relacionados con la movilidad.

![Ficha movilidad.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Ficha movilidad.")

1.  Haga clic en el botón **Opciones avanzadas** junto a **movilidad (UCWA)**. Establezca el campo **UcwaTargetServerUrl** en la dirección IP virtual (VIP) del grupo de directores o en la VIP del grupo de servidores front-end.

2.  En **presencia y audio de mensajería\\instantánea P2P**, seleccione el valor adecuado para el **nivel de carga** para habilitar la simulación de escenario de movilidad.

<div>


> [!NOTE]  
> Cada uno de los escenarios tiene un botón <STRONG>avanzado</STRONG> situado junto a él. Estos botones permiten el acceso a valores específicos de cada escenario que cambiarán el comportamiento de la herramienta stress and performance de Lync Server 2013 (LyncPerfTool) y habilitación de la personalización. Para cada uno de los escenarios de Reach, si el <STRONG>nivel de carga</STRONG> es <STRONG>personalizado</STRONG>, se usa el valor especificado en el campo <STRONG>ConversationsPerHour</STRONG> en lugar del predeterminado.



</div>

</div>

<div>

## <a name="summary"></a>Resumen

La ficha **Resumen** de la herramienta de configuración de carga de Lync Server 2013 se muestra en la siguiente figura.

![Ficha Resumen.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Ficha Resumen.")

La pestaña **Resumen** indica qué usuarios deben usar para cada uno de los escenarios. Es posible configurar manualmente los intervalos de números de usuario activando la casilla de verificación **Habilitar la generación de intervalo de usuario personalizado** y, a continuación, haciendo doble clic en el escenario de la tabla que tiene el **intervalo de usuarios** que desea personalizar. Compruebe (RunClient. bat) Agregue un retraso de inicio de sesión al iniciar el, a fin de incluir retrasos en los archivos por lotes generados para que correspondan a la tasa de inicio de sesión. Esto es útil para evitar la sobrecarga del servidor al iniciar sesión en un gran número de usuarios. Haga clic en **generar archivos**y seleccione la carpeta en la que desea generar la configuración. Cuando los archivos se hayan creado correctamente, aparecerá un cuadro de diálogo similar a la siguiente figura.

![Confirmación de que se han creado los archivos.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Confirmación de que se han creado los archivos.")

</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear usuarios y contactos](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
