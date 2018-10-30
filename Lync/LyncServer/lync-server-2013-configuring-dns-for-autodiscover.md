---
title: Configurar DNS para la detección automática
TOCTitle: Configurar DNS para la detección automática
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945656(v=OCS.15)
ms:contentKeyID: 52061966
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar DNS para la detección automática

 

_**Última modificación del tema:** 2012-12-12_

Para admitir la detección automática de clientes de Lync, debe crear los siguientes registros del Sistema de nombres de dominio (DNS):

  - Un registro DNS interno para admitir clientes de Lync que se conectan desde la red de su organización

  - Un registro DNS externo, o público, para admitir clientes de Lync que se conectan desde Internet

Debe crear un registro DNS interno y un registro DNS externo para cada dominio SIP.

Los registros DNS pueden ser registros de host (A) o registros CNAME, según cuál sea su capacidad para crear certificados con el nombre alternativo del firmante (SAN) adicional. En caso de que no pueda solicitar e implementar un nuevo certificado externo (público) con el SAN lyncdiscover.\<nombre de dominio\>, recurra al procedimiento para usar el puerto HTTP/TCP 80. Con los siguientes procedimientos se explica cómo crear registros DNS internos y externos.

## Para crear registros CNAME de DNS

1.  Inicie sesión en un servidor DNS de la siguiente manera:
    
      - Para crear un registro DNS interno, inicie sesión en un servidor DNS de la red como miembro del grupo Admins. del dominio o miembro del grupo DnsAdmins.
    
      - Para crear un registro DNS externo, conéctese a su proveedor de DNS público.

2.  Abra el complemento administrativo de DNS: haga clic en **Iniciar**, en **Herramientas administrativas** y en **DNS**.

3.  Siga uno de estos procedimientos:
    
      - Si es un registro DNS interno, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** de su dominio de Active Directory (por ejemplo, contoso.local).
        

        > [!NOTE]
        > Este dominio es el dominio de Active Directory donde el grupo de Director de Lync Server 2013 y el Grupo de servidores front-end se instalan.

    
      - Si es un registro DNS externo, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** de su dominio SIP (por ejemplo, contoso.com).

4.  Compruebe que haya un registro de host A para el Grupo de directores de la manera siguiente:
    
      - Si es un registro DNS interno, debería haber un registro de host A relativo al nombre de dominio completo (FQDN) interno de servicios web del Grupo de directores (por ejemplo, lyncwebdir01.contoso.local).
    
      - Si es un registro DNS externo, debería haber un registro de host A relativo al FQDN externo de servicios web del Grupo de directores (por ejemplo, lyncwebextdir.contoso.com).

5.  Compruebe que haya un registro de host A para el Grupo de servidores front-end de la manera siguiente:
    
      - Si es un registro DNS interno, debería haber un registro de host A para el FQDN interno de servicios web del Grupo de servidores front-end (por ejemplo, lyncwebpool01.contoso.local).
    
      - Si es un registro DNS externo, debería haber un registro de host A relativo al FQDN externo de servicios web del Grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).

6.  Si es un registro DNS interno, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** del dominio SIP (por ejemplo, contoso.com).
    

    > [!NOTE]
    > Si crea un registro DNS externo, <STRONG>Zonas de búsqueda directa</STRONG> ya está expandido en el dominio SIP desde el paso&nbsp;3.



7.  Haga clic con el botón secundario en el nombre de dominio SIP y, a continuación, haga clic en **Nuevo alias (CNAME)**.

8.  En **Nombre de alias**, escriba una de las siguientes opciones:
    
      - Si es un registro DNS interno, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.
    
      - Si es un registro DNS externo, escriba lyncdiscover como nombre de host para la dirección URL externa del servicio Detección automática.

9.  En **Nombre de dominio completo (FQDN) para el host de destino**, realice una de las operaciones siguientes:
    
      - Si es un registro DNS interno, escriba o busque el FQDN interno de servicios web del Grupo de directores (por ejemplo, lyncwebdir01.contoso.local) y haga clic en **Aceptar**.
    
      - Si es un registro DNS externo, escriba o busque el FQDN externo de servicios web del Grupo de directores (por ejemplo, lyncwebextdir.contoso.com) y haga clic en **Aceptar**.
    

    > [!NOTE]
    > Si no usa un Director, use el FQDN interno y externo de servicio web del Grupo de servidores front-end o, para un único servidor único, el FQDN del Servidor front-end o el Servidor Standard Edition.

    
    > [!IMPORTANT]  
    > Debe crear un nuevo registro CNAME de Detección automática en la zona de búsqueda directa de cada dominio SIP que admita en su entorno de Lync Server 2013.
    


## Para crear registros DNS A

1.  Inicie sesión en un servidor DNS de la siguiente manera:
    
      - Para crear un registro DNS interno, inicie sesión en un servidor DNS de la red como miembro del grupo Admins. del dominio o miembro del grupo DnsAdmins.
    
      - Para crear un registro DNS externo, conéctese a su proveedor de DNS público o servidor DNS externo.

2.  Abra el complemento administrativo de DNS: haga clic en **Iniciar**, en **Herramientas administrativas** y en **DNS**.

3.  Realice una de las siguientes acciones:
    
      - En el caso de un registro DNS interno, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** de su dominio de Active Directory (por ejemplo, contoso.local).
        

        > [!NOTE]
        > Este dominio es el dominio de Active Directory donde el grupo de Director de Lync Server 2013 y el Grupo de servidores front-end se instalan.

    
      - En el caso de un registro DNS externo, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** de su dominio SIP (por ejemplo, contoso.com).

4.  Compruebe que haya un registro de host A (para IPv6, AAAA) correspondiente al Grupo de directores de la manera siguiente:
    
      - Si es un registro DNS interno, debería haber un registro de host A (para IPv6, AAAA) relativo al nombre de dominio completo (FQDN) interno de servicios web del Grupo de directores (por ejemplo, lyncwebdir01.contoso.local).
    
      - Si es un registro DNS externo, debería haber un registro de host A (para IPv6, AAAA) relativo al FQDN externo de servicios web del Grupo de directores (por ejemplo, lyncwebextdir.contoso.com).

5.  Compruebe que haya un registro de host A (para IPv6, AAAA) correspondiente al Grupo de servidores front-end de la manera siguiente:
    
      - Si es un registro DNS interno, debería haber un registro de host A (para IPv6, AAAA) relativo al FQDN interno de servicios web del Grupo de servidores front-end (por ejemplo, lyncwebpool01.contoso.local).
    
      - Si es un registro DNS externo, debería haber un registro de host A (para IPv6, AAAA) relativo al FQDN externo de servicios web del Grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).

6.  En el caso de un registro DNS interno, en el árbol de la consola del servidor DNS, expanda **Zonas de búsqueda directa** del dominio SIP (por ejemplo, contoso.com).
    

    > [!NOTE]
    > Si crea un registro DNS externo, <STRONG>Zonas de búsqueda directa</STRONG> ya está expandido en el dominio SIP desde el paso&nbsp;3.



7.  Haga clic con el botón secundario en el nombre de dominio SIP y, a continuación, haga clic en **Nuevo host (A o AAAA)**.

8.  En **Nombre**, escriba el nombre de host de la siguiente manera:
    
      - Si es un registro DNS interno, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.
    
      - Si es un registro DNS externo, escriba lyncdiscover como nombre de host para la dirección URL externa del servicio Detección automática.
    

    > [!NOTE]
    > El nombre de dominio se deduce de la zona en la que se define el registro y, por lo tanto, no es necesario introducirlo como parte del registro&nbsp;A.



9.  En **Dirección IP**, escriba la dirección IP de la siguiente manera:
    
      - Si es un registro DNS interno, escriba la dirección IP interna de servicios web del Director (o, si usa un equilibrador de carga, escriba la IP virtual (VIP) del equilibrador de carga del Director).
        

        > [!NOTE]
        > Si no usa un Director, escriba la dirección IP del Servidor front-end o Servidor Standard Edition o, si usa un equilibrador de carga, escriba la VIP del equilibrador de carga del Grupo de servidores front-end.

    
      - Si es un registro DNS externo, escriba la dirección IP externa o pública del proxy inverso.

10. Haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.

11. Para crear más registros A, repita los pasos del 8 al 10.
    
    > [!IMPORTANT]  
    > Debe crear registros A de lyncdiscover y lyncdiscoverinternal en la zona de búsqueda directa de cada dominio SIP que admita en su entorno de Lync Server 2013.
    


12. Cuando termine de crear registros A (para IPv6, AAAA), haga clic en **Listo**.

