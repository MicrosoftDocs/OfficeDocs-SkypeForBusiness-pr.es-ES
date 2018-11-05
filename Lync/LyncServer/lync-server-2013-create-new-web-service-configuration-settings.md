---
title: Creación de opciones de configuración nuevas para un servicio web
TOCTitle: Creación de opciones de configuración nuevas para un servicio web
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48277171
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación de opciones de configuración nuevas para un servicio web

 

_**Última modificación del tema:** 2012-11-01_

Puede utilizar la página **Servicio web** para configurar los métodos de autenticación para obtener acceso a servidores web relacionados con Lync Server 2013 y a servicios web.

Siga estos pasos para crear una nueva directiva de servicios web.

## Para crear una directiva de servicios web

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Servicio web**.

4.  En la página **Servicio web**, haga clic en **Nuevo** y, a continuación, realice una de las siguientes acciones:
    
      - Para configurar el servicio web para un sitio, haga clic en **Configuración del sitio**. En **Seleccionar un sitio**, haga clic en el sitio al que se aplicará la directiva de servicios web y, a continuación, haga clic en **Aceptar**.
    
      - Para configurar el servicio web para un grupo de servidores, haga clic en **Configuración del grupo de servidores**. En **Seleccionar un servicio**, haga clic en el servicio al que se aplicará la directiva de servicios web y, a continuación, haga clic en **Aceptar**.

5.  En **Nueva configuración de servicio web**, en **Autenticación de Windows**, seleccione **Negociar**, **NTLM** o **Ninguna**.

6.  Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.
    
      - **Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.
    
      - **Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.
    
      - **Habilitar descarga de cadena de certificados** para que los servidores se presenten con un certificado de autenticación, descargue la cadena de certificados para ese certificado.

7.  Haga clic en **Confirmar**.

