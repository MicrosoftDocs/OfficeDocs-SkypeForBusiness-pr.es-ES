---
title: 'Lync Server 2013: Crear y comprobar registros DNS SRV'
TOCTitle: Crear y comprobar registros DNS SRV
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48275910
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear y comprobar registros DNS SRV en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o dominio, al menos, como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.

En este tema se describe cómo configurar los registros del Sistema de nombres de dominio (DNS) que necesita crear en las implementaciones de Lync Server 2013 y los necesarios para el inicio de sesión automático de los clientes. Al crear un Grupo de servidores front-end, la instalación crea objetos y configuraciones de Active Directory para el grupo de servidores, como el nombre de dominio completo (FQDN) del grupo de servidores. Se crean objetos y configuraciones similares para un Servidor Standard Edition. Para que los clientes puedan conectarse al grupo de servidores o el Servidor Standard Edition, el FQDN del grupo de servidores o del Servidor Standard Edition se debe registrar en DNS. Debe crear registros DNS SRV en su DNS interno para cada dominio SIP. En este procedimiento, se presupone que el DNS interno tiene zonas para los dominios de usuarios SIP.

## Para configurar un registro DNS SRV

1.  En el servidor DNS, haga clic en **Inicio** , **Herramientas administrativas** y, a continuación, en **DNS** .

2.  En el árbol de consola del dominio SIP, expanda **Zonas de búsqueda directa** y, a continuación, haga clic con el botón secundario en el dominio SIP donde vaya a instalar Lync Server 2013.

3.  Haga clic en **Otros nuevos registros** .

4.  En **Seleccione el tipo de registro del recurso** , haga clic en **Ubicación de servicio (SRV)** y, a continuación, haga clic en **Crear registro** .

5.  Haga clic en **Servicio** y escriba **\_sipinternaltls** .

6.  Haga clic en **Protocolo** y, a continuación, escriba **\_tcp** .

7.  Haga clic en **Número de puerto** y, a continuación, escriba **5061** .

8.  Haga clic en **Host que ofrece este servicio** y, a continuación, escriba el FQDN del grupo de servidores o el Servidor Standard Edition.

9.  Haga clic en **Aceptar** y, a continuación, haga clic en **Listo** .

## Para comprobar la creación de un registro DNS SRV

1.  Inicie sesión en un equipo cliente del dominio con una cuenta que sea miembro del grupo Usuarios autenticados o que tenga permisos equivalentes.

2.  Haga clic en **Inicio** y en **Ejecutar** .

3.  En el cuadro **Abrir** , escriba **cmd** y, a continuación, haga clic en **Aceptar** .

4.  En el símbolo del sistema, escriba **nslookup** y, a continuación, presione ENTRAR.

5.  Escriba **set type=srv** y, a continuación, presione ENTRAR.

6.  Escriba **\_sipinternaltls.\_tcp.contoso.com** y, a continuación, presione ENTRAR. El resultado que se muestra para el registro de Seguridad de la capa de transporte (TLS) es el siguiente:
    
    Servidor: *\<dns server\>* .contoso.com
    
    Dirección: *\<dirección IP del servidor DNS\>*
    
    Respuesta no autoritativa:
    
    \_sipinternaltls.\_tcp.contoso.com Ubicación del servicio SRV:
    
    prioridad = 0
    
    peso = 0
    
    puerto = 5061
    
    nombre de host svr = poolname.contoso.com (o registro A del servidor Standard Edition)
    
    poolname.contoso.com Dirección de Internet = *\<dirección IP virtual del equilibrador de carga\>* o *\<dirección IP de un único servidor Enterprise Edition para grupos de servidores que solo tengan un servidor Enterprise Edition\>* o *\<la dirección IP del grupo de servidores Standard Edition\>*

7.  Cuando termine, en el símbolo del sistema, escriba **exit** y, a continuación, presione ENTRAR.

## Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition

1.  Inicie sesión en un equipo cliente en el dominio.

2.  Haga clic en **Inicio** y en **Ejecutar** .

3.  En el cuadro **Abrir** , escriba **cmd** y, a continuación, haga clic en **Aceptar** .

4.  En el símbolo del sistema, escriba **nslookup** *\<FQDN del grupo de servidores front-end\>* o *\<FQDN del servidor Standard Edition\>* y, a continuación, presione ENTRAR.

5.  Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.

