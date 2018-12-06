---
title: "Lync Server 2013: Configuración XMPP de ejemplo - Federación XMPP con Google Talk"
TOCTitle: Configuración XMPP de ejemplo - Federación XMPP con Google Talk
ms:assetid: 360a2f7b-015b-4e93-ac67-0f609c21f1a2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204807(v=OCS.15)
ms:contentKeyID: 48274908
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración XMPP de ejemplo en Lync Server 2013 - Federación XMPP con Google Talk

 

_**Última modificación del tema:** 2016-12-08_

Una configuración de ejemplo para implementar el proxy XMPP define una federación con Google Talk.

## Configuración XMPP de ejemplo - Federación XMPP con Google Talk

1.  En el Servidor front-end, abra el Asistente para la implementación de Lync Server. Haga clic en **Instalar** o en **Actualizar Lync Server System** y, a continuación, en **Instalar** o **Quitar componentes de Lync Server**. Haga clic en **Ejecutar de nuevo**.

2.  En **Instalar componentes de Lync Server**, haga clic en **Siguiente**. La pantalla de resumen mostrará las acciones a medida que se ejecuten. Una vez completada la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles. Haga clic en **Finalizar** para completar la implementación.

3.  En el Servidor perimetral, abra el Asistente para la implementación de Lync Server. Haga clic en **Instalar** o en **Actualizar Lync Server System** y, a continuación, en **Instalar** o **Quitar componentes de Lync Server**. Haga clic en **Ejecutar de nuevo**.

4.  Añada Google Talk como socio XMPP permitido. Google solo admite actualmente conexiones TCP sin cifrar para la federación XMPP de servidor a servidor y solo admite Server Dialback para la verificación de la identidad. (Consulte <http://xmpp.org/extensions/xep-0220.html>).
    
        New-CsXmppAllowedPartner gmail.com -TlsNegotiation NotSupported -SaslNegotiation NotSupported -EnableKeepAlive $false -SupportDialbackNegotiation $true

5.  Para habilitar la federación perimetral, escriba lo siguiente:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $true

6.  En **Instalar componentes de Lync Server**, haga clic en **Siguiente**. La pantalla de resumen mostrará las acciones a medida que se ejecuten. Una vez realizada la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles. Haga clic en **Finalizar** para completar la implementación.

7.  En el Servidor perimetral, en el Asistente para la implementación de Lync Server, junto al **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.
    
    > [!TIP]  
    > Si es la primera vez que implementa el servidor perimetral, aparecerá Ejecutar en lugar de Ejecutar de nuevo.
    


8.  En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.

9.  En la página **Solicitud de certificado**, haga clic en **Certificado perimetral externo**.

10. En la página **Solicitud retrasada o inmediata**, active la casilla **Prepare ahora la solicitud, pero enviarla más tarde**.

11. En la página **Archivo de solicitud de certificados**, escriba la ruta de acceso completa y el nombre del archivo en el que se guardará la solicitud (por ejemplo, c:\\cert\_exernal\_edge.cer).

12. En la página **Especificar plantilla de certificado alternativa**, para usar una plantilla distinta a la plantilla predeterminada WebServer, active la casilla **Usar plantilla de certificado alternativa para la entidad de certificación seleccionada**.

13. En la página **Nombre y configuración de seguridad**, siga este procedimiento:
    
    1.  En **Nombre descriptivo**, escriba un nombre para mostrar para el certificado
    
    2.  En **Longitud de bits**, especifique la longitud de bits (normalmente, el valor predeterminado es **2048**)
    
    3.  Asegúrese de que la casilla de verificación **Marcar la clave privada del certificado como exportable** está seleccionada.

14. En la página **Información de la organización**, escriba un nombre para la organización y la unidad organizativa (por ejemplo, una división o un departamento)

15. En la página **Información geográfica**, escriba la información de ubicación

16. En la página **Nombre de sujeto/nombres alternativos de sujeto**, la información se rellenará automáticamente gracias al asistente que se muestra. Si necesita otros nombres alternativos de sujeto, especifíquelos en los dos pasos siguientes

17. En la página **Configuración del dominio SIP en nombres alternativos de sujeto (SAN)**, active la casilla del dominio para agregar una entrada sip. *\<sipdomain\>* a la lista de nombres alternativos de sujeto.

18. En la página **Configurar nombres alternativos de sujeto adicionales**, especifique cualquier nombre alternativo del firmante adicional que necesite.
    
    > [!TIP]  
    > Si el proxy de XMPP está instalado, las entradas SAN se cumplimentan de forma predeterminada con el nombre de dominio (por ejemplo, contoso.com). Si necesita más entradas, agréguelas en este paso.
    


19. En la página **Resumen de la solicitud**, revise la información del certificado que va a usar para generar la solicitud.

20. Cuando finalice la ejecución de los comandos, puede seleccionar la opción **Ver registro** o hacer clic en **Siguiente** para continuar.

21. En la página **Archivo de solicitud de certificados**, puede ver el archivo de solicitud de firma de certificado (CSR) que se ha generado. Para ello, haga clic en **Ver** o haga clic en **Finalizar** para salir del Asistente para certificados.

22. Copie el archivo de solicitud y envíelo a la entidad de certificación pública.

23. Una vez recibido, importado y asignado el certificado público, debe detener y reiniciar los servicios del servidor perimetral. Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.. En el Shell de administración de Lync Server, escriba:
    
    ```
    Stop-CsWindowsService
    ```
    ```
    Start-CsWindowsService
    ```

24. Para configurar DNS para la federación XMPP, añada el siguiente registro SRV al DNS externo:\_xmpp-server.\_tcp. *\<domain name\>* El registro SRV se resolverá en el FPDN perimetral de acceso del servidor perimetral, con un valor de puerto de 5269

25. Configure una nueva directiva de acceso externo para habilitar a todos los usuarios para abrir el Shell de administración de Lync Server en el Servidor front-end escribiendo lo siguiente:
    
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAccess $true -EnablePublicCloudAccess $true
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic

