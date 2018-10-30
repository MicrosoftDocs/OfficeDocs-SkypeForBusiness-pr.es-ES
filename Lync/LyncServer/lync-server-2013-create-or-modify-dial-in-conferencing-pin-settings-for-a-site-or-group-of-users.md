---
title: "Configuración de PIN de conferencia telefónica para un sitio o grupo de usuarios"
TOCTitle: Crear o modificar la configuración de PIN de conferencia de acceso telefónico local para un sitio o grupo de usuarios
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48276583
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar la configuración de PIN de conferencia de acceso telefónico local para un sitio o grupo de usuarios en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-18_

Siga los pasos a continuación para crear o modificar una directiva de número de identificación personal (PIN) de conferencias de acceso telefónico local a nivel de usuario o a nivel de sitio. Para obtener información detallada sobre cómo modificar la directiva de PIN global, consulte [Modificar la configuración del PIN de la conferencia de acceso telefónico local predeterminada en Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).

## Para crear una directiva de PIN de usuario o sitio

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Directiva de PIN** .

4.  En la página **Directiva de PIN** , haga clic en **Nueva** y, a continuación, siga uno de los procedimientos siguientes:
    
      - Para crear una directiva de nivel de usuario, haga clic en **Directiva de usuario** . En **Nueva directiva de PIN** , en **Nombre** , escriba un nombre descriptivo para la directiva.
    
      - Para crear una directiva de nivel de sitio, haga clic en **Directiva de sitio** . En el campo de búsqueda **Seleccionar un sitio** , escriba todo o parte del nombre del sitio para el que desea crear una directiva. En la lista de sitios, haga clic en el sitio que desee y, a continuación, en **Aceptar** .

5.  En el campo **Descripción** , escriba una descripción de la directiva de PIN.

6.  En el campo **Longitud mínima de PIN** , escriba o seleccione la longitud mínima de PIN que desee permitir. La longitud mínima predeterminada es de cinco dígitos.

7.  Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla **Especificar máximo de intentos de inicio de sesión** . Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.

8.  Si activa la casilla **Especificar máximo de intentos de inicio de sesión** en **Máximo de intentos de inicio de sesión** , escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.

9.  Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN** . Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.

10. Si activa la casilla **Habilitar expiración de PIN** , en **el PIN expira después de (días)** ; escriba o seleccione el número de días después de los cuales expira el PIN.

11. En **Recuento de historial de PIN** , escriba el número de PIN que debe crear un usuario antes de que pueda volver a utilizar el PIN. De forma predeterminada, los usuarios pueden volver a utilizar sus PIN.

12. Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, números secuenciales y conjuntos repetitivos de números, active la casilla **Permitir patrones comunes** . Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.
    
    > [!IMPORTANT]  
    > Se recomienda no permitir patrones comunes.
    


13. Haga clic en **Confirmar** .

## Para modificar una directiva de PIN de usuario o sitio nueva

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Directiva de PIN** .

4.  En la página **Directiva de PIN** , haga clic en la directiva de PIN que desee modificar, haga clic en **Editar** y, a continuación, en **Mostrar detalles** .

5.  En **Editar directiva de PIN** , modifique cualquier configuración de directivas (salvo el nombre de la directiva, que no se puede modificar).

6.  Haga clic en **Confirmar** .

