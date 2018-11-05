---
title: 'Lync Server 2013: Configurar la federación XMPP'
TOCTitle: Configurar la federación XMPP
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48275422
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la federación XMPP en Lync Server 2013

 

_**Última modificación del tema:** 2012-12-03_

Para implementar el proxy XMPP en el servidor perimetral, debe configurar el servidor perimetral para la federación de XMPP. Para ello, siga estos pasos.

## Configuración de federación XMPP

1.  Inicie sesión en el equipo donde se encuentre instalado el Asistente para la implementación de Lync Server como miembro del grupo de administradores del dominio y el grupo RTCUniversalServerAdmins.

2.  En el servidor front-end, abra al Asistente para implementación de Lync Server. Haga clic en Instalar o actualizar el sistema Lync Server y, a continuación, haga clic en Instalar o desinstalar componentes de Lync Server. Haga clic en Ejecutar de nuevo.

3.  En Instalar componentes de Lync Server, haga clic en Siguiente. La pantalla de resumen mostrará las acciones a medida que se ejecuten. Una vez finalizada la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en Finalizar para completar la implementación.

4.  En el servidor perimetral, abra el asistente para la implementación de Lync Server. Haga clic en Instalar o en Actualizar Lync Server System y, a continuación, en Instalar o desinstalar componentes de Lync Server. Haga clic en Ejecutar nuevamente.

5.  En Instalar componentes de Lync Server, haga clic en Siguiente. La pantalla de resumen mostrará las acciones a medida que se ejecuten. Una vez finalizada la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en Finalizar para completar la implementación.

6.  En el Asistente para la implementación del servidor perimetral, junto a Paso 3: Solicitar, instalar o asignar certificados, haga clic en Ejecutar de nuevo.
    
    > [!TIP]  
    > Si es la primera vez que implementa el servidor perimetral, aparecerá Ejecutar en lugar de Ejecutar de nuevo.
    


7.  En la página Tareas de certificado disponibles, haga clic en Crear una nueva solicitud de certificado.

8.  En la página Solicitud de certificado, haga clic en Certificado perimetral externo.

9.  En la página Solicitud retrasada o inmediata, active la casilla Prepare ahora la solicitud, pero enviarla más tarde.

10. En la página Archivo de solicitud de certificados, escriba la ruta de acceso completa y el nombre del archivo en el que se guardará la solicitud (por ejemplo, c:\\cert\_exernal\_edge.cer).

11. En la página Especificar plantilla de certificado alternativa, para usar una plantilla distinta a la plantilla predeterminada WebServer, active la casilla Usar plantilla de certificado alternativa para la entidad de certificación seleccionada.

12. En la página Nombre y configuración de seguridad, siga este procedimiento:
    
    1.  En Nombre descriptivo, escriba un nombre para mostrar para el certificado
    
    2.  En Longitud de bits, especifique la longitud de bits (normalmente, el valor predeterminado es 2048)
    
    3.  Asegúrese de que la casilla de verificación Marcar la clave privada del certificado como exportable está seleccionada.

13. En la página Información de la organización, escriba un nombre para la organización y la unidad organizativa (por ejemplo, una división o un departamento)

14. En la página Información geográfica, escriba la información de ubicación

15. En la página Nombre de sujeto/nombres alternativos de sujeto, la información se rellenará automáticamente gracias al asistente que se muestra. Si necesita otros nombres alternativos de sujeto, especifíquelos en los dos pasos siguientes

16. En la página Configuración de dominio SIP en nombres alternativos de sujeto (SAN), active la casilla del dominio para agregar una entrada sip.\<dominiosip\> a la lista de nombres alternativos del firmante.

17. En la página Configurar nombres alternativos de sujeto adicionales, especifique los nombres alternativos de sujeto adicionales que sean necesarios.
    
    > [!TIP]  
    > Si el proxy de XMPP está instalado, las entradas SAN se cumplimentan de forma predeterminada con el nombre de dominio (por ejemplo, contoso.com). Si necesita más entradas, agréguelas en este paso.
    


18. En la página Resumen de la solicitud, revise la información del certificado que va a usar para generar la solicitud.

19. Una vez que los comandos terminen de ejecutarse, puede Ver el registro o hacer clic en Siguiente para continuar.

20. En la página Archivo de solicitud de certificados, puede ver el archivo de solicitud de firma de certificado (CSR) que se ha generado. Para ello, haga clic en Ver o haga clic en Finalizar para salir del Asistente para certificados.

21. Copie el archivo de solicitud y envíelo a la entidad de certificación pública.

22. Después de recibir, importar y asignar el certificado público, debe detener y reiniciar los servicios del servidor perimetral. Para ello, escriba en la consola de administración de Lync Server:
    
    ```
    Stop-CsWindowsService
    ```
    ```
    Start-CsWindowsService
    ```

23. Para configurar DNS para la federación de XMPP, agregue el siguiente registro SRV al DNS externo\_xmpp-server.\_tcp.\<nombre de dominio\>. El registro SRV se resolverá en el FQDN perimetral de acceso del servidor perimetral con un valor de puerto de 5269. Además, configure un registro de host 'A' (por ejemplo, xmpp.contoso.com) que señale a la dirección IP del servidor perimetral de acceso.
    
    > [!IMPORTANT]  
    > Si tiene grupos de servidores perimetrales en varios sitios, conviene agregar varios registros SRV para la federación de XMPP. Agregue un registro SRV por cada grupo de servidores perimetrales que haya en la organización y asigne a cada uno de ellos una prioridad distinta. Cuando todos los grupos de servidores perimetrales estén ejecutándose, el que tenga la máxima prioridad se encargará de todas las solicitudes XMPP, pero si está inactivo, no será necesario agregar un nuevo registro SRV para recobrar la funcionalidad de federación de XMPP.
    


24. Configurar una nueva directiva de acceso externo para habilitar a todos los usuarios abriendo la Consola de administración de Lync Server en el servidor front-end y escriba:
    
    ```
    New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
    ```
    ```
    New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
    ```
    ```
    Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
    ```

    Habilite el acceso de XMPP para usuarios externos escribiendo:
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
    ```
    ```
    Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
    ```

25. En el Servidor perimetral en el que se haya implementado el proxy XMPP, abra un símbolo del sistema o una Interfaz de línea de comandos de Windows PowerShell™ y escriba lo siguiente:
    
    ```
    Netstat -ano | findstr 5269
    ```
    ```
    Netstat -ano | findstr 23456
    ```
    
    El comando **netstat –ano** es un comando de estadísticas de red; los parámetros **–ano** solicitan que netstat muestre todas las conexiones y puertos de escucha (las direcciones y puertos se muestran en un formato numérico) y el identificador del proceso asociado a cada conexión. El carácter **|** define la canalización al siguiente comando, **findstr** (o cadena de búsqueda). Los números 5269 y 23456 que se pasan a findstr como parámetro indican a findstr que busque en el resultado de netstat las cadenas 5269 y 23456. Si XMPP está bien configurado, el resultado de los comandos debería reflejar las escuchas y las conexiones establecidas tanto en la interfaz externa (puerto 5269) como en la interfaz interna (puerto 23456) del Servidor perimetral.
    
    Si los comandos no devuelven unos puertos establecidos y de escucha en 5269 y 23456, compruebe lo siguiente:

## Solucionar problemas de la federación XMPP

1.  Haga lo siguiente para saber si el proxy XMPP se está ejecutando:

2.  Inicie sesión en el servidor perimetral que ejecuta el servicio de proxy XMPP como miembro del grupo del administrador local.

3.  Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Herramientas administrativas** y **Servicios**.

4.  En Servicios, busque el proxy de puerta de enlace de traducción de XMPP de Lync Server. Este servicio debe estar en estado **Iniciado** ; si no lo está, haga clic en el icono **Iniciar** de la barra de herramientas. El icono se mostrará como una flecha verde que apunta hacia la derecha.

5.  Confirme que el servicio ha cambiado a **Iniciado** . Si así es, cierre **Servicios** y prosiga.
    
    Si el servicio no se ha iniciado, abra el Visor de eventos desde Herramientas administrativas y consulte los errores y advertencias en la sección **Lync Server** de **Registros de aplicaciones y servicios** .

6.  Cuando el servicio **Puerta de enlace de traducción de XMPP de Lync Server** se esté ejecutando, vuelva a comprobar los comandos netstat que empleamos anteriormente. Si no ve que se establezcan o escuchen sesiones, compruebe y asegúrese de que la opción **Ruta de federación XMPP** está correctamente configurada en el Generador de topologías.

7.  Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.

8.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

9.  En el Generador de topologías, seleccione el sitio de la ruta de federación XMPP y revise para confirmar que la opción **Asignación de ruta de federación del sitio** en **Federación XMPP** refleja su Servidor perimetral o Grupo de servidores perimetrales como la asignación de ruta de federación XMPP seleccionada.
    
    Si la asignación de ruta es incorrecta o no se ha establecido, haga clic con el botón secundario en el sitio y haga clic en **Editar propiedades** . Active la casilla de federación XMPP y, después, seleccione el Servidor perimetral o Grupo de servidores perimetrales adecuado.

10. Publique la topología. Para obtener información detallada, consulte [Publicar una topología en Lync Server 2013](lync-server-2013-publish-your-topology.md)
    
    > [!TIP]  
    > Aunque no suele ser necesario, puede que deba reiniciar los Servidores perimetrales.
    


11. Con el proceso netstat, confirme que el Servidor perimetral escucha o establece sesiones en los puertos 5269 y 23456.

12. Si sigue sin ver las sesiones que espera, consulte el Visor de eventos para ver las causas que pueden intervenir en el problema de comunicación.

## Vea también

#### Tareas

[Configuración XMPP de ejemplo en Lync Server 2013 - Federación XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### Otros recursos

[Administrar socios federados XMPP para su organización en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

