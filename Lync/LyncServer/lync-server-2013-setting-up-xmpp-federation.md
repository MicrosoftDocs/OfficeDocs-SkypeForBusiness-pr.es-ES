---
title: 'Lync Server 2013: Configurar la federación XMPP'
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
ms.openlocfilehash: fd61aded33d37e4a1f5f58e9050f3cd62794f9b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>Configurar la federación XMPP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-03_

Para implementar el proxy XMPP en el servidor perimetral, debe configurar el servidor perimetral para la Federación de XMPP. Para ello, siga estos pasos.

<div>

## <a name="setting-up-xmpp-federation"></a>Configuración de la Federación XMPP

1.  Inicie sesión en el equipo donde está instalado el Asistente para la implementación de Lync Server como miembro del grupo administradores de dominio y el grupo RTCUniversalServerAdmins.

2.  En el servidor front-end, abra el Asistente para la implementación de Lync Server. Haga clic en instalar o actualizar el sistema Lync Server y, a continuación, haga clic en configurar o quitar los componentes de Lync Server. Vuelva a hacer clic en ejecutar.

3.  En instalación de los componentes de Lync Server, haga clic en siguiente. La pantalla resumen mostrará las acciones a medida que se ejecutan. Una vez que haya finalizado la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en finalizar para completar la implementación.

4.  En el servidor perimetral, abra el Asistente para la implementación de Lync Server. Haga clic en instalar o actualizar el sistema Lync Server y, a continuación, haga clic en configurar o quitar los componentes de Lync Server. Vuelva a hacer clic en ejecutar.

5.  En instalación de los componentes de Lync Server, haga clic en siguiente. La pantalla resumen mostrará las acciones a medida que se ejecutan. Una vez que haya finalizado la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en finalizar para completar la implementación.

6.  En el servidor perimetral, en el Asistente para la implementación, junto al paso 3: solicitar, instalar o asignar certificados, haga clic en ejecutar de nuevo.
    
    <div class=" ">
    

    > [!TIP]  
    > Si está implementando el servidor perimetral por primera vez, verá ejecutar en lugar de volver a ejecutar.

    
    </div>

7.  En la página Tareas de certificado disponibles, haga clic en Crear una nueva solicitud de certificado.

8.  En la página solicitud de certificado, haga clic en certificado de borde externo.

9.  En la página solicitud inmediata o demorada, active la casilla preparar la solicitud ahora pero enviarla más tarde.

10. En la página archivo de solicitud de certificado, escriba la ruta de acceso completa y el nombre del archivo en el que se va a guardar la solicitud (por\\ejemplo\_,\_c: CERT la Edge. cer).

11. En la página especificar plantilla de certificado alternativa, para usar una plantilla distinta de la plantilla predeterminada de WebServer, seleccione la casilla Usar plantilla de certificado alternativa para la entidad emisora de certificados seleccionada.

12. En la página   Nombre y configuración de seguridad, siga este procedimiento:
    
    1.  En nombre descriptivo, escriba un nombre para mostrar para el certificado.
    
    2.  En longitud bit, especifique la longitud en bits (normalmente, el valor predeterminado de 2048).
    
    3.  Compruebe que la casilla marcar clave privada de certificado como exportable está seleccionada

13. En la página información de la organización, escriba el nombre de la organización y la unidad organizativa (por ejemplo, una división o un departamento).

14. En la página información geográfica, especifique la información de ubicación

15. En la página nombre de sujeto/nombres alternativos de asunto, se muestra la información que el asistente rellenará automáticamente. Si se necesitan nombres alternativos de asunto adicionales, debe especificarlos en los dos pasos siguientes.

16. En la página Configuración del dominio SIP en la página de nombres alternativos de asunto (San), seleccione la casilla dominio para agregar un SIP. \<sipdomain\> entrada a la lista de nombres alternativos de asunto.

17. En la página configurar otros nombres alternativos de asunto, especifique los nombres alternativos de asunto adicionales necesarios
    
    <div class=" ">
    

    > [!TIP]  
    > Si el proxy XMPP está instalado, de forma predeterminada, el nombre de dominio (por ejemplo, contoso.com) se rellena en las entradas SAN. Si necesita más entradas, agréguelos en este paso.

    
    </div>

18. En la página solicitar Resumen, revise la información del certificado que se va a usar para generar la solicitud.

19. Cuando termine de ejecutarse los comandos, puede ver el registro o hacer clic en siguiente para continuar.

20. En la página de archivo de solicitud de certificado, puede ver el archivo de solicitud de firma de certificado generado (CSR) haciendo clic en ver o salir del asistente de certificados haciendo clic en finalizar.

21. Copie el archivo de solicitud y envíelo a la entidad emisora de certificados pública.

22. Después de recibir, importar y asignar el certificado público, debe detener y reiniciar los servicios del servidor perimetral. Esto se hace escribiendo en la consola de administración de Lync Server:
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. Para configurar DNS para la Federación XMPP, agregue el siguiente registro SRV a DNS externo:\_XMPP-Server. \_TCP. \<nombre\> de dominio el registro SRV se resolverá en el FQDN perimetral de acceso del servidor perimetral, con un valor de puerto de 5269. Además, puede configurar un registro de host ' A ' (por ejemplo, xmpp.contoso.com) que apunte a la dirección IP del servidor perimetral de acceso.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Si tiene grupos de bordes en varios sitios, le recomendamos que agregue varios registros SRV para la Federación XMPP. Agregue un registro SRV para cada grupo perimetral de su organización y asigne una prioridad diferente a cada uno de los registros SRV. Cuando se ejecutan todos los grupos de bordes, las solicitudes XMPP se gestionarán en el grupo Edge con la primera prioridad, pero si ese grupo de Edge deja de funcionar, no tendrá que agregar un nuevo registro SRV para recuperar la funcionalidad de Federación de XMPP.

    
    </div>

24. Configure una nueva Directiva de acceso externo para habilitar a todos los usuarios abriendo el shell de administración de Lync Server en el front-end y escribiendo lo siguiente:
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    Habilite el acceso XMPP para los usuarios externos escribiendo:
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. En el servidor perimetral donde se implementa el proxy XMPP, abra un símbolo del sistema o una interfaz de línea de comandos de Windows PowerShell™ y escriba lo siguiente:
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    El comando **netstat – ano** es un comando de estadísticas de red, los parámetros **– ano** solicitar que netstat muestre todas las conexiones y los puertos de escucha, la dirección y los puertos se muestran en un formato numérico, y que el identificador del proceso propietario está asociado con cada conexión. El carácter **|** define una canalización para el siguiente comando, **Findstr**o Find String. El número 5269 y 23456 que se pasa a Findstr como parámetro indica a Findstr que busque en la salida de netstat las cadenas 5269 y 23456. Si XMPP está configurado correctamente, el resultado de los comandos debe dar como resultado conexiones y conexiones establecidas, tanto en la interfaz externa (puerto 5269) como en la interfaz interna (puerto 23456) del servidor perimetral.
    
    Si los comandos no devuelven puertos establecidos o que atienden en 5269 y 23456, compruebe lo siguiente:

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>Solución de problemas de Federación de XMPP

1.  Para determinar si el proxy XMPP se está ejecutando, haga lo siguiente:

2.  Inicie sesión en el servidor perimetral que está ejecutando el servicio de proxy XMPP como miembro del grupo de administradores locales.

3.  Haga clic en **Inicio**, en **todos los programas**, en **herramientas administrativas**y en **servicios** .

4.  En servicios, localice el proxy de puerta de enlace de Lync Server XMPP. El servicio debe estar en estado de **Inicio** . Si no se ha iniciado, haga clic en el icono **Inicio** de la barra de herramientas. El icono aparece como una flecha verde que señala hacia la derecha.

5.  Confirme que el servicio ha cambiado a **iniciado**. Si se ha iniciado correctamente, cierra **servicios** y continúa.
    
    Si el servicio no se ha iniciado correctamente, en herramientas administrativas, abra visor de eventos y consulte los errores y advertencias en la parte de **Lync Server** en **registros de aplicaciones y servicios**.

6.  Una vez que se esté ejecutando el servicio de **puerta de enlace de Lync Server XMPP** , vuelva a comprobar los comandos netstat usados previamente. Si no ve las sesiones de establecimiento o escucha, compruebe y asegúrese de que la **ruta de Federación de XMPP** esté correctamente configurada en el generador de topología

7.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

8.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

9.  En el generador de topologías, seleccione el sitio de la ruta y revisión de la Federación XMPP para confirmar que la asignación de enrutamiento de la **Federación de sitios** para la **Federación XMPP** muestra el servidor perimetral o el grupo perimetral como la asignación de ruta de Federación XMPP seleccionada.
    
    Si la asignación de ruta es incorrecta o no está configurada, haga clic con el botón secundario en el sitio y haga clic en **Editar propiedades**. Seleccione la casilla Federación de XMPP y, a continuación, seleccione el servidor perimetral o el grupo de límites correctos.

10. Publique la topología. Para obtener más información, vea [publicar una topología en Lync Server 2013](lync-server-2013-publish-your-topology.md)
    
    <div class=" ">
    

    > [!TIP]  
    > Aunque no es obligatorio y generalmente no es necesario, es posible que tenga que reiniciar los servidores perimetrales

    
    </div>

11. Con el proceso de netstat usado anteriormente, confirme que el servidor perimetral está escuchando o ha establecido sesiones en el puerto 5269 y en el puerto 23456.

12. Si sigue sin ver las sesiones esperadas, compruebe en el visor de eventos si se producen posibles causas de contribución por el problema de comunicación.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración XMPP de ejemplo en Lync Server 2013 - Federación XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Administrar socios federados XMPP para su organización en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

