---
title: Modificación de la configuración de un servicio web existente
TOCTitle: Modificación de la configuración de un servicio web existente
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48276511
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modificación de la configuración de un servicio web existente

 

_**Última modificación del tema:** 2012-11-01_

Puede utilizar la página **Servicio web** para configurar los métodos de autenticación para obtener acceso a servidores web relacionados con Lync Server 2013 y a servicios web.

Siga estos pasos para modificar una directiva de servicio web existente.

## Para modificar un servicio web existente

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Servicio web**.

4.  En la página **Servicio web**, haga clic en una configuración, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración de servicio web**, en **Autenticación de Windows**, seleccione **Negociar**, **NTLM** o **Ninguno**.

6.  Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.
    
      - **Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.
    
      - **Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.
    
      - **Habilitar descarga de cadena de certificados** para que los servidores se presenten con un certificado de autenticación, descargue la cadena de certificados para ese certificado.

7.  Haga clic en **Confirmar**.

## Vea también

#### Otros recursos

[Configurar seguridad en el panel de control de Lync Server 2013](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)

