---
title: "Asignación de certificado de autenticación servidor a servidor a MS Lync Server 2013"
TOCTitle: "Attr. d’un certif. d’auth. de serveur à serveur à Microsoft Lync Server 2013"
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48276633
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignación de un certificado de autenticación servidor a servidor a Microsoft Lync Server 2013

 

_**Última modificación del tema:** 2013-10-24_

Para determinar si ya se ha asignado a Microsoft Lync Server 2013 un certificado de autenticación de servidor a servidor, ejecute el comando siguiente desde Shell de administración de Lync Server 2013:

    Get-CsCertificate -Type OAuthTokenIssuer

Si no recibe información del certificado, debe asignar un certificado del emisor de token para poder usar la autenticación de servidor a servidor. Como norma general, se puede usar cualquier certificado de Lync Server 2013 como certificado OAuthTokenIssuer (por ejemplo, el certificado predeterminado de Lync Server 2013 también se puede usar como certificado OAuthTokenIssuer). Asimismo, el certificado OAuthTokenIssuer puede ser cualquier certificado de servidor web que incluya el nombre del dominio SIP en el campo Asunto. Los dos requisitos principales del certificado que se use para la autenticación de servidor a servidor son: 1) como certificado OAuthTokenIssuer, debe configurarse el mismo certificado en todos los servidores front-end; 2) el certificado debe tener al menos 2048 bits.

Si no dispone de un certificado que pueda usarse para la autenticación de servidor a servidor, puede obtener uno nuevo, importarlo y usarlo para este tipo de autenticación. Una vez haya solicitado y obtenido el nuevo certificado, podrá iniciar sesión en cualquiera de los servidores front-end y usar un comando de Windows PowerShell similar a este para importar y asignar el certificado:

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

En el comando anterior, el parámetro Path representa la ruta de acceso completa al archivo de certificado, y el parámetro Password representa la contraseña que se asignó al certificado. Este procedimiento debe ejecutarse una sola vez: el servicio de replicación de Lync Server creará automáticamente un conjunto de tareas programadas que descifrarán e implementarán el certificado en todos los servidores front-end.

También puede usar un certificado actual como certificado de autenticación de servidor a servidor. Como se ha mencionado, el certificado predeterminado se puede usar como certificado de autenticación de servidor a servidor. Los dos comandos siguientes de Windows PowerShell recuperan el valor de la propiedad Thumbprint del certificado predeterminado. Use este valor para que el certificado predeterminado sea el certificado de autenticación de servidor a servidor:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

En el comando anterior, el certificado recuperado está configurado para funcionar con certificado de autenticación de servidor a servidor global. Esto significa que el certificado se replicará en todos los servidores front-end y que se usará en ellos. Recuerde que este comando solo debe ejecutarse una vez en los servidores front-end. Aunque todos los servidores front-end deben usar el mismo certificado, no debe configurar el certificado OAuthTokenIssuer en cada servidor front-end. Configure el certificado una vez y deje que el servidor de replicación de Lync Server se ocupe de copiarlo en cada uno de los servidores.

El cmdlet Set-CsCertificate toma el certificado en cuestión e inmediatamente configura dicho certificado para que actúe como el certificado OAuthTokenIssuer actual. Lync Server 2013 conserva dos copias de un tipo de certificado: el certificado actual y el anterior. Si necesita que el nuevo certificado empiece a actuar de forma inmediata como certificado OAuthTokenIssuer, debe usar el cmdlet Set-CsCertificate.

También puede usar el cmdlet Set-CsCertificate para la "sucesión" de un nuevo certificado. "Sucesión" significa simplemente que se configura un nuevo certificado para que pase a ser el certificado OAuthTokenIssuer actual en un momento determinado. Por ejemplo, este comando recupera el certificado predeterminado y lo configura para que sea el certificado OAuthTokenIssuer actual a partir del 1 de julio de 2012:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

El 1 de julio de 2012, el nuevo certificado se configurará como el certificado OAuthTokenIssuer actual, y el "antiguo" certificado OAuthTokenIssuer se configurará como el certificado anterior.

Si no quiere usar Windows PowerShell, puede usar la consola MMC de certificados para exportar un certificado del servidor front-end e importarlo a todos los servidores front-end. Si lo hace así, no olvide exportar la clave privada junto con el propio certificado.

> [!CAUTION]  
> En tal caso, el procedimiento debe hacerse en cada servidor front-end. Si los certificados se exportan e importan de este modo, Lync Server 2013 no los replicará en cada servidor front-end.



Una vez que el certificado se haya importado en todos los servidores front-end, se podrá asignar con el Asistente para la implementación de Lync Server, en lugar de con Windows PowerShell. Para asignar un certificado con el Asistente para la implementación, siga estos pasos en un equipo donde este asistente esté instalado:

1.  Haga clic en Inicio, en Todos los programas, en **Microsoft Lync Server 2013** y en **Asistente para la implementación de Lync Server**.

2.  En el Asistente para la implementación, haga clic en **Instalar o actualizar sistema Lync Server**.

3.  En la página Microsoft Lync Server 2013, haga clic en el botón **Ejecutar** bajo el encabezado **Paso 3: Solicitar, instalar o asignar certificados**. Nota: si ya ha instalado certificados en este equipo, en lugar del botón **Ejecutar**, aparecerá **Ejecutar de nuevo**.

4.  En el Asistente para certificados, seleccione el certificado **OAuthTokenIssuer** y haga clic en **Asignar**.

5.  En la página **Asignación de certificado** del Asistente para certificados, haga clic en **Siguiente**.

6.  En la página **Almacén de certificados**, seleccione el certificado que desea usar para la autenticación de servidor a servidor y haga clic en **Siguiente**.

7.  En la página Resumen de asignación de certificados, haga clic en **Siguiente**.

8.  En la página Ejecución de comandos, haga clic en **Finalizar**.

9.  Cierre el Asistente para certificados y el Asistente para la implementación.

