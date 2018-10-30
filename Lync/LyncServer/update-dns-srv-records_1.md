---
title: Actualizar registros DNS SRV
TOCTitle: Actualizar registros DNS SRV
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49889513
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Actualizar registros DNS SRV

 

_**Última modificación del tema:** 2012-09-29_

Para completar correctamente este procedimiento, debe iniciar sesión en el servidor o dominio como miembro del grupo Admins. del dominio o como miembro del grupo DnsAdmins.

En este tema se explica cómo actualizar los registros del sistema de nombres de dominio (DNS) después de migrar a Lync Server 2013. Tras mover a todos los usuarios a Lync Server 2013, pero antes de retirar el Director o grupo de servidores de Office Communications Server 2007 R2 heredado, deberá actualizar los registros SRV de DNS en su DNS interno para cada dominio SIP. En este procedimiento se presupone que el DNS interno tiene zonas para los dominios de usuarios SIP.

**Para configurar un registro DNS SRV**

1.  En el servidor DNS, haga clic en **Inicio** , **Herramientas administrativas** y, a continuación, en **DNS** .

2.  En el árbol de consola de su dominio SIP, expanda **Zonas de búsqueda directa** , expanda el dominio SIP donde esté instalado Lync Server 2013 y vaya al parámetro de configuración **\_tcp**.

3.  En el panel derecho, haga clic con el botón secundario en **\_sipinternaltls** y seleccione **Propiedades**.

4.  En **Host que ofrece este servicio** , actualice el FQDN del host de manera que apunte al grupo de servidores de Lync Server 2013.

5.  Haga clic en **Aceptar** .

**Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition**

1.  Inicie sesión en un equipo cliente en el dominio.

2.  Haga clic en **Inicio** y en **Ejecutar** .

3.  En el cuadro **Abrir** , escriba **cmd** y, a continuación, haga clic en **Aceptar** .

4.  En el símbolo del sistema, escriba **nslookup** *\<FQDN del grupo de servidores front-end\>* o *\<FQDN del servidor Standard Edition\>* y, a continuación, presione ENTRAR.

5.  Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.

