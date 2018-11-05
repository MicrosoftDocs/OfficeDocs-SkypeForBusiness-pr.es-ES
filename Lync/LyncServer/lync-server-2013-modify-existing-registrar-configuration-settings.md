---
title: "Modif. des paramètres de configuration d’un serveur d’inscriptions existant"
TOCTitle: "Modif. des paramètres de configuration d’un serveur d’inscriptions existant"
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48276295
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modificación de las opciones de configuración de un registrador existente

 

_**Última modificación del tema:** 2012-11-01_

Puede usar el registrador para configurar los protocolos de autenticación del servidor proxy. Para obtener información sobre los protocolos disponibles, consulte [Creación de opciones de configuración de un registrador](lync-server-2013-create-registrar-configuration-settings.md).


> [!NOTE]
> Se recomienda habilitar Kerberos y NTLM cuando un servidor admita la autenticación para los clientes remotos y de empresa. El servidor perimetral y los servidores internos se comunican para garantizar que solamente se ofrezca la autenticación NTLM a clientes remotos. Si solamente se habilita Kerberos en estos servidores, no podrán autenticar usuarios remotos. Si los usuarios de empresa también se autentican frente al servidor, se usa Kerberos.



Siga los pasos a continuación para modificar un registrador existente.

## Para modificar un registrador existente

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.

4.  En la página **Registrador**, haga clic en un servicio, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración de registrador**, seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno:
    
      - **Habilitar autenticación Kerberos**: para que los servidores del grupo emitan desafíos mediante la autenticación Kerberos.
    
      - **Habilitar autenticación NTLM**: para que los servidores del grupo emitan desafíos mediante la autenticación NTLM.
    
      - **Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.

6.  Haga clic en **Confirmar**.

