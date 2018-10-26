---
title: Creación de opciones de configuración de un registrador
TOCTitle: Creación de opciones de configuración de un registrador
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48277084
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación de opciones de configuración de un registrador

 

_**Última modificación del tema:** 2013-03-17_

Puede usar el registrador para configurar los métodos de autenticación de servidores proxy. El protocolo de autenticación que especifique definirá el tipo de desafío que presentarán los servidores del grupo a los clientes. Los protocolos disponibles son:

  - **Kerberos** es el esquema de autenticación por contraseña más seguro de los esquemas disponibles para los clientes pero, en general, solo está disponible para los clientes empresariales, ya que requiere una conexión de cliente a un centro de distribución de claves (controlador de dominio de Kerberos). Esta configuración es adecuada si el servidor autentica solo clientes empresariales.

  - **NTLM** es el esquema de autenticación por contraseña que está disponible para los clientes y usa un esquema hash de desafío/respuesta en la contraseña. Se trata de la única forma de autenticación disponible para los clientes sin conectividad a un centro de distribución de claves (controlador de dominio de Kerberos), como los usuarios remotos. Si un servidor autentica únicamente a usuarios remotos, se recomienda elegir NTLM.

  - **Autenticación de certificado**   es el nuevo método de autenticación, en el que el servidor necesita obtener certificados de los clientes de Lync Phone Edition, teléfonos de área común y Lync 2013. En los clientes de Lync Phone Edition, cuando un usuario inicia sesión y se autentica correctamente facilitando un número de identificación personal (PIN), Lync Server 2013 aprovisiona el URI del SIP al teléfono y aprovisiona un certificado firmado de Lync Server o un certificado de usuario que identifique a Joe (ej.: SN=joe@contoso.com) al teléfono. Este certificado se usa para la autenticación con el registrador y los Servicios web.


> [!NOTE]
> Se recomienda habilitar Kerberos y NTLM cuando un servidor admita la autenticación para los clientes remotos y de empresa. El servidor perimetral y los servidores internos se comunican para garantizar que solamente se ofrezca la autenticación NTLM a clientes remotos. Si solamente se habilita Kerberos en estos servidores, no podrán autenticar usuarios remotos. Si los usuarios de empresa también se autentican frente al servidor, se usa Kerberos.



Siga estos pasos para crear un registrador nuevo.

## Para crear un registrador

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o se asigne al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.

4.  En la página **Registrador**, haga clic en **Nuevo**.

5.  En **Seleccionar un servicio** , haga clic en el servicio al que se aplicará el Registrador y, a continuación, haga clic en **Aceptar** .

6.  En **Nueva configuración de registrador**, seleccione uno o más de los siguientes elementos en función de las funciones de los clientes y la compatibilidad de su entorno:
    
      - **Habilitar autenticación Kerberos**: para que los servidores del grupo emitan desafíos mediante la autenticación Kerberos.
    
      - **Habilitar autenticación NTLM**: para que los servidores del grupo emitan desafíos mediante la autenticación NTLM.
    
      - **Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.

7.  Haga clic en **Confirmar**.

