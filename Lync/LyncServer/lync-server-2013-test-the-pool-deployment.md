---
title: 'Lync Server 2013: Probar la implementación del grupo de servidores'
TOCTitle: Probar la implementación del grupo de servidores
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48277304
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Probar la implementación del grupo de servidores en Lync Server 2013

 

_**Última modificación del tema:** 2013-09-25_

En el siguiente procedimiento se describe cómo probar la implementación de Grupo de servidores front-end.

## Para probar la implementación del grupo

1.  Use el complemento Usuarios y equipos de Active Directory para agregar el objeto de usuario de Active Directory del rol de administrador para la implementación de Lync Server 2013 (en el que el Panel de control de Lync Server 2013 está instalado) al grupo **CSAdministrator**.
    
    > [!IMPORTANT]  
    > Si no agrega los usuarios y los grupos adecuados al grupo CsAdministors, recibirá un mensaje de error al abrir el Panel de control de Lync Server, que dice “No autorizado: acceso denegado por error en la autorización del control de acceso basado en roles (RBAC)”.
    


2.  Si el objeto de usuario ha iniciado sesión, cierre sesión y, a continuación, vuelva a iniciar sesión para registrar la nueva asignación de grupo.
    

    > [!NOTE]
    > La cuenta de usuario no puede ser el administrador local de ningún servidor en el que se ejecute Lync Server 2013.



3.  Use la cuenta administrativa para iniciar sesión en el equipo donde está instalado el Panel de control de Lync Server.

4.  Inicie el Panel de control de Lync Server y proporcione credenciales, si se solicitan. El Panel de control de Lync Server muestra la información sobre la implementación.

5.  En la barra de navegación izquierda, haga clic en **Topología**. A continuación, confirme que el estado de servicio sea un icono de equipo con una flecha verde, y que exista una marca de verificación verde para estado de replicación junto a cada rol del servidor de Lync Server que se haya implementado y puesto en línea.

6.  En la barra de navegación izquierda, haga clic en **Usuarios** y haga clic en **Habilitar usuarios**.

7.  En la página **Nuevo usuario de Lync Server**, haga clic en **Agregar**.

8.  Para definir parámetros de búsqueda de los objetos que quiera encontrar, en la página **Seleccionar de Active Directory** seleccione **Buscar** y, si lo desea, haga clic en **Agregar filtro**. También puede seleccionar **Búsqueda LDAP** y especificar una expresión de LDAP para filtrar o limitar los objetos que se devolverán. Una vez establecidas las opciones de búsqueda, haga clic en **Buscar**.

9.  En en el panel de resultados de la búsqueda, seleccione todos los objetos de esta sesión de búsqueda y haga clic en **Aceptar**.

10. En la página **Nuevo usuario de Lync Server** el objeto o los objetos seleccionados están en la pantalla **Usuarios**. En la lista **Asignar usuarios a un grupo**, seleccione el servidor en el que se deben hospedar los objetos.
    
    A continuación se presentan una serie de opciones para configurar los objetos.
    
      - **Generar el URI del SIP del usuario**
    
      - **Telefonía**
    
      - **URI de línea**
    
      - **Directiva de conferencia**
    
      - **Directiva de versión de clientes**
    
      - **Directiva de PIN**
    
      - **Directiva de acceso externo**
    
      - **Directiva de archivado**
    
      - **Directiva de ubicación**
    
      - **Directiva de cliente**
    
    Para probar la funcionalidad básica, seleccione la opción que prefiera para el parámetro **Generar el URI del SIP de usuario** (las otras opciones de la configuración usan los valores predeterminados) y haga clic en **Habilitar**.

11. En pantalla se muestra una página de resumen con una marca de verificación en la columna **Habilitado** para indicar que los objetos ya están listos para usarse. En la columna **Dirección SIP** figura la dirección que se necesita para configurar el inicio de sesión del usuario.

12. Un usuario debe iniciar sesión en un equipo integrado en el dominio y otro usuario, en otro equipo del dominio.

13. Instale Lync 2013 en los dos equipos cliente y compruebe que los dos usuarios puedan iniciar sesión en Lync Server 2013 y que puedan enviarse mensajes instantáneos.

## Vea también

#### Conceptos

[Implementación de clientes y dispositivos en Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)

