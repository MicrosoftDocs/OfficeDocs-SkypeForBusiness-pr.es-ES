---
title: 'Lync Server 2013: Configurar certificados para servidores'
TOCTitle: Configurar certificados para servidores
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48276924
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar certificados para servidores en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario miembro del grupo RTCUniversalServerAdmins o tener los permisos correctos delegados. Para más información sobre la delegación de permisos, vea [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Es probable que deba pertenecer a otros grupos en función de su organización y los requisitos para solicitar certificados. Consúltelo con el grupo que administra la entidad de certificación de la infraestructura de clave pública (PKI).


> [!NOTE]
> Lync Server 2013 es compatible con el conjunto de aplicaciones SHA-2 (SHA-2 usa síntesis con longitudes de 224, 256, 384 o 512 bits) de algoritmos hash y de firma de síntesis para las conexiones de clientes que ejecutan los sistemas operativos Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista o Windows XP, además deLync Phone Edition. Para permitir el acceso externo mediante el conjunto de aplicaciones SHA-2, el certificado externo lo emite una CA pública que también puede emitir un certificado con las mismas longitudes de bits de síntesis.



> [!CAUTION]  
> La selección de la síntesis de hash y el algoritmo de firma depende de los clientes y de los servidores que usarán el certificado y de otros equipos y dispositivos con los que los clientes y servidores se comunicarán, quienes también deben saber cómo usar los algoritmos del certificado. Para más información sobre qué longitudes de síntesis son compatibles en el sistema operativo y en algunas aplicaciones cliente, vea <a href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</a>.



Cada Servidor Standard Edition o Servidor front-end necesita hasta cuatro certificados: el certificado oAuthTokenIssuer, un certificado predeterminado, un certificado web interno y un certificado web externo. No obstante, es posible solicitar y asignar un solo certificado predeterminado con las entradas de nombre alternativo de sujeto apropiadas, así como con el certificado oAuthTokenIssuer. Para más información sobre los requisitos de certificado, vea [Requisitos de certificado para Servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md). Para más información sobre la solicitud, asignación e instalación del certificado oAuthTokenIssuer, vea [Administración de la autenticación servidor a servidor (Oauth) y las aplicaciones de socio en Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).

Ejecute el procedimiento siguiente para solicitar, asignar e instalar los certificados de Servidor Standard Edition o de Servidor front-end. Repita el procedimiento por cada Servidor front-end.

> [!IMPORTANT]  
> En el siguiente procedimiento se describe cómo configurar certificados desde una PKI de empresa interna implementada por su organización y sin necesidad de conexión para procesar solicitudes. Para más información sobre la obtención de certificados emitidos por una CA pública, vea <a href="lync-server-2013-certificate-requirements-for-internal-servers.md">Requisitos de certificado para Servidores internos en Lync Server 2013</a> en la documentación referente a la planeación. Asimismo, se describe cómo solicitar, asignar e instalar certificados durante la instalación del Servidor front-end. Si ya solicitó certificados por adelantado con el procedimiento descrito en la sección <a href="lync-server-2013-request-certificates-in-advance-optional.md">Solicitar los certificados con anterioridad (opcional) para Lync Server 2013</a> de esta documentación de implementación o si no usa una PKI de empresa interna implementada en su organización para obtener certificados, modifique este procedimiento según corresponda.



## Para configurar certificados para un servidor front-end

1.  En el Asistente para la implementación de Lync Server, haga clic en **Ejecutar** junto a **Paso 3: Solicitar, instalar o asignar certificados**.

2.  En la página **Asistente para certificados**, haga clic en **Solicitud**.

3.  En la página**Solicitud de certificado**, haga clic en**Siguiente**.

4.  En la página **Solicitudes retrasadas o inmediatas**, acepte la opción predeterminada **Envíe la solicitud inmediatamente a una entidad de certificación en línea** haciendo clic en **Siguiente**. La CA interna con inscripción en línea automática debe estar disponible si selecciona esta opción. Si elige la opción para retrasar la solicitud, se le pedirá un nombre y una ubicación para guardar el archivo de solicitud de certificado. La solicitud de certificado debe ser presentada y procesada por una CA de su organización o bien por una CA pública. Después, tendrá que importar la respuesta de certificado y asignarla al rol de certificado apropiado.

5.  En la página **Elija una entidad de certificación (CA)**, seleccione la opción **Seleccionar una entidad de certificación de la lista detectada en el entorno** y después seleccione una CA conocida (a través del registro en Servicios de dominio de Active Directory) de la lista. O bien, seleccione la opción **Especificar otra entidad de certificación**, escriba el nombre de otra CA en el cuadro y haga clic en **Siguiente**.

6.  En la página **Cuenta de entidad de certificación**, se solicitan sus credenciales para solicitar y procesar la solicitud de certificado en la CA. Debe haber determinado si es necesario un nombre de usuario y una contraseña para solicitar un certificado por adelantado. Su administrador de CA tendrá la información necesaria y es posible que deba ayudarle en este paso. Si tiene que especificar credenciales alternativas, seleccione la casilla, escriba un nombre de usuario y una contraseña en los cuadros de texto y haga clic en **Siguiente**.

7.  En la página **Especificar plantilla de certificado alternativa**, haga clic en **Siguiente** para usar la plantilla de servidor web predeterminada.
    

    > [!NOTE]
    > Si su organización ha creado una plantilla para usar como alternativa a la plantilla de la CA de servidor web predeterminada, seleccione la casilla y escriba el nombre de la plantilla alternativa. Necesitará el nombre de la plantilla definido por el administrador de CA.



8.  En la página **Nombre y configuración de seguridad**, especifique un **Solo nombre** que debe permitirle identificar el certificado y el propósito. Si lo deja en blanco, se generará un nombre automáticamente. Establezca la **Longitud en bits** de la clave o acepte el valor predeterminado de 2048 bits. Active la casilla **Marcar la clave privada del certificado como exportable** si determina que el certificado y la clave privada deben moverse o copiarse a otros sistemas y haga clic en **Siguiente**.
    

    > [!NOTE]
    > Lync Server 2013 tiene requisitos mínimos para una clave privada exportable. Uno de estos sitios se encuentra en los servidores perimetrales en un grupo de servidores, donde el servicio de autenticación relé multimedia usa copias del certificado, en lugar de certificados individuales para cada instancia en el grupo de servidores.



9.  En la página **Información de la organización**, si lo desea, proporcione información de la organización y después haga clic en **Siguiente**.

10. En la página **Información geográfica**, si lo desea, escriba información geográfica y después haga clic en **Siguiente**.

11. En la página **Nombre del sujeto o nombres alternativos del sujeto**, revise los nombres alternativos del sujeto que se van a agregar y haga clic en **Siguiente**.

12. En la página **Configuración del dominio SIP**, active la casilla **Dominio SIP** y haga clic en **Siguiente**.

13. En la página **Configurar nombres alternativos de sujeto adicionales**, agregue los nombres alternativos de sujeto adicionales que desee, incluido cualquiera que piense que puede ser necesario para dominios SIP adicionales en el futuro, y haga clic en **Siguiente**.

14. En la página **Resumen de la solicitud de certificados**, revise la información del resumen. Si la información es correcta, haga clic en **Siguiente**. Si necesita corregir o modificar una configuración, haga clic en **Atrás** para ir a la página pertinente y realizar la corrección o modificación.

15. En la página **Ejecución de comandos**, haga clic en **Siguiente**.

16. En la página**Estado de solicitud del certificado en línea** , revise la información devuelta. Tenga en cuenta que el certificado se emitió e instaló en el almacén de certificados local. Si se indica que se ha emitido e instalado, pero que no es válido, compruebe que el certificado raíz de la CA se haya instalado en el almacén de la raíz de confianza del servidor. Consulte la documentación de la CA para obtener información sobre cómo recuperar un certificado de CA de raíz de confianza. Si necesita ver el certificado recuperado, haga clic en **Ver detalles del certificado** . La casilla **Asignar este certificado a los usos de certificado de Lync Server** está activada de forma predeterminada. Si desea asignar manualmente el certificado, active la casilla y haga clic en **Finalizar** .

17. Si ha activado la casilla **Asignar este certificado a los usos de certificado de Lync Server** en la página anterior, aparecerá la página **Asignación del certificado**. Haga clic en **Siguiente**.

18. En la página **Almacén de certificados**, seleccione el certificado solicitado. Si desea ver el certificado, haga clic en **Ver detalles del certificado** y en **Siguiente** para continuar.
    

    > [!NOTE]
    > Si en la página <STRONG>Estado de solicitud del certificado en línea</STRONG> se ha notificado algún problema con el certificado, como que el certificado no es válido, ver el certificado real puede resultarle de ayuda para resolver el problema. Dos problemas específicos que pueden hacer que un certificado no sea válido son que falte el certificado de CA de raíz de confianza mencionado anteriormente o que falte una clave privada asociada con el certificado. Consulte la documentación de su CA para resolver estos dos problemas.



19. En la página **Resumen de asignación de certificados** , revise la información proporcionada para garantizar que este sea el certificado que debe asignarse y haga clic en **Siguiente** .

20. En la página **Ejecutando comandos**, revise el resultado del comando. Haga clic en **Ver registro** si desea revisar el proceso de asignación o si se ha emitido algún error o advertencia. Cuando termine, haga clic en **Finalizar**.

21. En la página **Asistente para certificados** , compruebe que el **Estado** del certificado sea “Asignado” y haga clic en **Cerrar** .

## Vea también

#### Otros recursos

[Requisitos de la infraestructura de certificados para Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md)

