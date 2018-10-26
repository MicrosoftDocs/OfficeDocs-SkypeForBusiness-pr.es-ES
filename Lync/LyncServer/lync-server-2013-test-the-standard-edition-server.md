---
title: 'Lync Server 2013: Comprobar el servidor Standard Edition'
TOCTitle: Comprobar el servidor Standard Edition
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48276436
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar el servidor Standard Edition en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-01_

En el siguiente procedimiento se describe cómo probar la implementación de un Servidor Standard Edition.

## Para probar la implementación de un servidor Standard Edition

1.  Use el complemento Usuarios y equipos de Active Directory para agregar el objeto de usuario de Active Directory del rol de administrador para la implementación de Lync Server 2013 (en el que el Panel de control de Lync Server está instalado) al grupo **CSAdministrator**.

2.  Si el objeto de usuario ha iniciado sesión, cierre sesión y, a continuación, vuelva a iniciar sesión para registrar la nueva asignación de grupo.
    

    > [!NOTE]
    > La cuenta de usuario no puede ser el administrador local del servidor en el que se ejecuta Lync Server 2013, Standard Edition. Si no agrega los usuarios y los grupos adecuados al grupo CsAdministors, aparecerá el siguiente mensaje de error al abrir el Panel de control de Lync Server 2013: "No autorizado: se ha denegado el acceso debido a un error en la autorización de control de acceso basado en roles (RBAC)".



3.  Use la cuenta administrativa para iniciar sesión en el equipo donde está instalado el Panel de control de Lync Server.

4.  Abra el Panel de control de Lync Server y proporcione las credenciales, si se solicitan. El Panel de control de Lync Server 2013 muestra información sobre la implementación.

5.  En la barra de navegación izquierda, haga clic en **Topología** , y confirme que el estado de servicio es un icono de equipo con una flecha verde y que hay una marca de verificación verde junto a cada rol del servidor de Lync Server que se ha implementado y conectado.

6.  En la barra de navegación izquierda, haga clic en **Usuarios** y habilite los dos usuarios para Lync Server 2013.

7.  Un usuario debe iniciar sesión en un equipo integrado en el dominio y el otro usuario, en otro equipo del dominio.

8.  Instale Lync Server 2013 en los dos equipos cliente y compruebe que los dos usuarios puedan iniciar sesión en Lync Server 2013 y que puedan enviarse mensajes instantáneos.

## Vea también

#### Conceptos

[Implementación de clientes y dispositivos en Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)

