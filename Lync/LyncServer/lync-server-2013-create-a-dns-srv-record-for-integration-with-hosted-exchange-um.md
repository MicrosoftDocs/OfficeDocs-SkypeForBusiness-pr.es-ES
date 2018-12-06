---
title: "Crear registro DNS SRV para integración con mensajería unific. hospedada de Exchange"
TOCTitle: Crear un registro DNS SRV para la integración con mensajería unificada (UM) hospedada de Exchange
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48275977
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear un registro DNS SRV para la integración con mensajería unificada (UM) hospedada de Exchange

 

_**Última modificación del tema:** 2016-12-08_

En este tema se describe cómo configurar el registro SRV del Sistema de nombres de dominio (DNS) necesario para enrutar un Lync Server 2013  Servidor perimetral a un servicio hospedado de Exchange como Microsoft Exchange Online.

## Para crear un registro SRV de DNS externo para el servicio Exchange hospedado

1.  Inicie sesión en el servidor DNS externo como miembro del grupo DnsAdmins.

2.  Haga clic en **Iniciar** , en **Herramientas administrativas** y en **DNS** .

3.  En el árbol de la consola de su dominio SIP, expanda **Zonas de búsqueda directa** y seleccione el dominio SIP en que se instalará Lync Server 2013.
    
    > [!IMPORTANT]  
    > Debe crear el registro SRV de DNS en el dominio SIP en que se va a instalar Lync Server. Al crear el registro SRV, el FQDN usado para el host que ofrece este campo de servicio debe ser el FQDN externo del grupo de servidores perimetrales. Por ejemplo, si el FQDN externo de su grupo de servidores perimetrales es edge01.contoso.net, escriba ese valor. Este debe estar también en el mismo dominio que el registro de host (A) de DNS.
    


4.  Haga clic con el botón secundario en el dominio seleccionado y haga clic en **Registros nuevos** .

5.  En **Tipo de registro del recurso** , haga clic en **Ubicación de servicio (SRV)** y en **Crear registro** .

6.  En **Nuevo registro de recursos** , haga clic en **Servicio** y escriba **\_sipfederationtls** .

7.  Haga clic en **Protocolo** y, a continuación, escriba **\_tcp**.

8.  Haga clic en **Número de puerto** y, a continuación, escriba **5061**.

9.  Haga clic en **Host que ofrece este servicio** y escriba el nombre de dominio completo (FQDN) del Lync Server 2013  Grupo de servidores perimetrales que proporciona acceso a su sistema Lync Server 2013 para clientes externos de confianza.
    

    > [!NOTE]
    > El dominio también debe estar configurado como un dominio aceptado y autoritativo en la configuración de Exchange Online. Para más información, vea Crear dominios aceptados en <A href="http://go.microsoft.com/fwlink/?linkid=229762%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=229762&amp;clcid=0xC0A</A>.



10. Haga clic en **Aceptar** y, a continuación, haga clic en **Listo** .

## Para comprobar que el registro SRV de DNS se ha creado correctamente

1.  Inicie sesión en un equipo cliente en el dominio.

2.  Haga clic en **Inicio** y en **Ejecutar** .

3.  En el símbolo del sistema, ejecute el comando siguiente:
    
        nslookup <FQDN Lync Edge Pool>

4.  Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.

## Vea también

#### Conceptos

[Crear registros DNS para servidores de proxy inverso en Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

