---
title: 'Lync Server 2013: configuración de la Federación XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cb6b2904ee2a8883c492e570173e73bc001cc03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497527"
---
# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>Configuración de la Federación XMPP en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-03_

Para implementar el proxy XMPP en el servidor perimetral, debe configurar el servidor perimetral para la federación de XMPP. Para ello, siga estos pasos.

<div>

## <a name="setting-up-xmpp-federation"></a>Configuración de la federación de XMPP

1.  Inicie sesión en el equipo en el que el asistente para la implementación de Lync Server esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

2.  En el servidor front-end, abra al Asistente para implementación de Lync Server. Haga clic en Instalar o actualizar el sistema Lync Server y, a continuación, haga clic en Instalar o desinstalar componentes de Lync Server. Haga clic en Ejecutar de nuevo.

3.  En Instalar componentes de Lync Server, haga clic en Siguiente. La pantalla de resumen mostrará las acciones a medida que se ejecutan. Una vez realizada la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en Finalizar para completar la implementación.

4.  En el servidor perimetral, abra el Asistente para implementación de Lync Server. Haga clic en Instalar o actualizar el sistema Lync Server y, a continuación, haga clic en Instalar o desinstalar componentes de Lync Server. Haga clic en Ejecutar de nuevo.

5.  En Instalar componentes de Lync Server, haga clic en Siguiente. La pantalla de resumen mostrará las acciones a medida que se ejecutan. Una vez realizada la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en Finalizar para completar la implementación.

6.  En el servidor perimetral, en el Asistente para implementación, junto al paso 3: petición, Solicitar, instalar o asignar certificados, haga clic en Ejecutar de nuevo.
    
    <div class=" ">
    

    > [!TIP]  
    > Si va a implementar el servidor perimetral por primera vez, verá Ejecutar en lugar de Ejecutar de nuevo.

    
    </div>

7.  En la página Tareas de certificado disponibles, haga clic en Crear una nueva solicitud de certificado.

8.  En la página solicitud de certificado, haga clic en certificado perimetral externo.

9.  En la página Solicitud retrasada o inmediata, seleccione la casilla Prepare ahora la solicitud, pero envíela más tarde.

10. En la página archivo de solicitud de certificado, escriba la ruta de acceso completa y el nombre de archivo del archivo en el que se va a guardar la solicitud (por ejemplo, c: \\ CERT \_ externos \_ Edge. cer).

11. En la página Especificar plantilla de certificado alternativa, para utilizar una plantilla distinta a la plantilla de servidor web predeterminada, seleccione la casilla Usar plantilla de certificado alternativa para la entidad de certificación seleccionada.

12. En la página Nombre y configuración de seguridad, haga lo siguiente:
    
    1.  En Nombre descriptivo, escriba un nombre para mostrar para el certificado.
    
    2.  En Longitud en bits, especifique la longitud en bits (normalmente, el valor predeterminado de 2048).
    
    3.  Compruebe que la casilla Marcar clave privada de certificado como exportable está activada.

13. En la página Información de la organización, escriba el nombre de la organización y la unidad organizativa (por ejemplo, una división o departamento).

14. En la página Información geográfica, especifique la información de ubicación.

15. En la página Nombre de sujeto / Nombres alternativos de sujeto se muestra la información que rellena automáticamente el asistente. Si son necesarios nombres alternativos de sujeto adicionales, debe especificarlos en los dos pasos siguientes.

16. En la página Configuración de dominio SIP en nombres alternativos de sujeto (San), active la casilla de verificación dominio para agregar un SIP.\<sipdomain\> entrada a la lista de nombres alternativos de sujeto.

17. En la página Configurar nombres alternativos de sujeto adicionales, especifique los nombres alternativos de sujeto adicionales que sean necesarios.
    
    <div class=" ">
    

    > [!TIP]  
    > Si está instalado el proxy XMPP, el nombre de dominio (por ejemplo, contoso.com) se rellena de forma predeterminada en las entradas de SAN. Si necesita más entradas, agréguelas en este paso.

    
    </div>

18. En la página Resumen de la solicitud, revise la información del certificado que se usará para generar la solicitud.

19. Después de que los comandos terminen de ejecutarse, puede elegir Ver registro o hacer clic en Siguiente para continuar.

20. En la página Archivo de solicitud de certificado, puede ver el archivo de solicitud de firma del certificado generado (CSR) haciendo clic en Ver o salir del Asistente para certificados haciendo clic en Finalizar.

21. opie el archivo de solicitud y envíeselo a su entidad emisora de certificación pública.

22. Después de recibir, importar y asignar el certificado público, debe detener y reiniciar los servicios del servidor perimetral. Para ello, escriba en la consola de administración de Lync Server:
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. Para configurar DNS para la Federación XMPP, agregue el siguiente registro SRV a DNS externo: \_ XMPP-Server. \_ TPC.\<domain name\> El registro SRV se resolverá en el FQDN perimetral de acceso del servidor perimetral, con un valor de puerto de 5269. Además, puede configurar un registro de host ' A ' (por ejemplo, xmpp.contoso.com) que señale a la dirección IP del servidor perimetral de acceso.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Si tiene grupos de servidores perimetrales en varios sitios, conviene agregar varios registros SRV para la federación de XMPP. Agregue un registro SRV por cada grupo de servidores perimetrales que haya en la organización y asigne a cada uno de ellos una prioridad distinta. Cuando todos los grupos de servidores perimetrales estén ejecutándose, el que tenga la máxima prioridad se encargará de todas las solicitudes XMPP, pero si está inactivo, no será necesario agregar un nuevo registro SRV para recobrar la funcionalidad de federación de XMPP.

    
    </div>

24. Configurar una nueva directiva de acceso externo para habilitar a todos los usuarios abriendo la Consola de administración de Lync Server en el servidor front-end y escriba:
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    Habilite el acceso de XMPP para usuarios externos escribiendo:
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. En el servidor perimetral en el que se implementa el proxy XMPP, abra un símbolo del sistema o una interfaz de línea de comandos de Windows PowerShell™ y escriba lo siguiente:
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    El comando **netstat –ano** es un comando de estadísticas de red; los parámetros **–ano** solicitan que netstat muestre todas las conexiones y puertos de escucha (las direcciones y puertos se muestran en un formato numérico) y el identificador del proceso asociado a cada conexión. El carácter **|** define una canalización para el siguiente comando, **Findstr**o Find String. El número 5269 y 23456 que se pasa a Findstr como parámetro indica a Findstr que busque en el resultado de netstat las cadenas 5269 y 23456. Si XMPP está configurado correctamente, el resultado de los comandos debe dar como resultado la escucha y la conexión establecida, tanto en la interfaz externa (puerto 5269) como en la interfaz interna (Port 23456) del servidor perimetral.
    
    Si los comandos no devuelven unos puertos establecidos y de escucha en 5269 y 23456, compruebe lo siguiente:

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>Solucionar problemas de la federación XMPP

1.  Haga lo siguiente para saber si el proxy XMPP se está ejecutando:

2.  Inicie sesión en el servidor perimetral que ejecuta el servicio de proxy XMPP como miembro del grupo del administrador local.

3.  Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Herramientas administrativas** y **Servicios**.

4.  En Servicios, busque el proxy de puerta de enlace de traducción de XMPP de Lync Server. Este servicio debe estar en estado **Iniciado**; si no lo está, haga clic en el icono **Iniciar** de la barra de herramientas. El icono se mostrará como una flecha verde que apunta hacia la derecha.

5.  Confirme que el servicio ha cambiado a **Iniciado**. Si así es, cierre **Servicios** y prosiga.
    
    Si el servicio no se ha iniciado, abra el Visor de eventos desde Herramientas administrativas y consulte los errores y advertencias en la sección **Lync Server** de **Registros de aplicaciones y servicios**.

6.  Cuando el servicio **Puerta de enlace de traducción de XMPP de Lync Server** se esté ejecutando, vuelva a comprobar los comandos netstat que empleamos anteriormente. Si no ve sesiones establecidas o en escucha, compruebe y asegúrese de que la **ruta de Federación de XMPP** esté correctamente configurada en el generador de topologías.

7.  Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

8.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

9.  En el generador de topologías, seleccione el sitio de la ruta de Federación XMPP y revise para confirmar que la **asignación de ruta de Federación del sitio** para la **Federación XMPP** muestra el servidor perimetral o el grupo de servidores perimetrales como la asignación de ruta de Federación XMPP seleccionada.
    
    Si la asignación de ruta es incorrecta o no se ha establecido, haga clic con el botón secundario en el sitio y haga clic en **Editar propiedades**. Active la casilla Federación XMPP y, a continuación, seleccione el servidor perimetral o el grupo de servidores perimetrales correctos.

10. Publique la topología. Para obtener más información, consulte [publicar la topología en Lync Server 2013](lync-server-2013-publish-your-topology.md)
    
    <div class=" ">
    

    > [!TIP]  
    > Aunque no es necesario y normalmente no es necesario, es posible que necesite reiniciar los servidores perimetrales.

    
    </div>

11. Con el proceso netstat usado anteriormente, confirme que el servidor perimetral ya está escuchando o ha establecido sesiones en los puertos 5269 y 23456.

12. Si sigue sin ver las sesiones que espera, consulte el Visor de eventos para ver las causas que pueden intervenir en el problema de comunicación.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Configuración XMPP de ejemplo en Lync Server 2013: Federación XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Administrar socios federados XMPP en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

