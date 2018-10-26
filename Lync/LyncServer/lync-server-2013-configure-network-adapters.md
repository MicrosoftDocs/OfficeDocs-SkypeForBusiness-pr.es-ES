---
title: 'Lync Server 2013: Configurar adaptadores de red'
TOCTitle: Configurar adaptadores de red
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48275507
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar adaptadores de red en Lync Server 2013

 

_**Última modificación del tema:** 2013-11-07_

Debe asignar una o varias direcciones IP al adaptador de red externo y al menos una dirección IP al adaptador de red interno.

En los siguientes procedimientos, el servidor que ejecuta Forefront Threat Management Gateway (TMG) 2010 o el enrutamiento de solicitud de aplicaciones de Internet Information Server tiene dos adaptadores de red:

  - Un adaptador de red pública, o externa, que se mostrará a los clientes que intenten conectarse a su sitio web (normalmente a través de Internet).

  - Una interfaz de red privada, o interna, para los servidores internos que ejecuten Lync Server y hospeden los servicios web.

> [!IMPORTANT]  
> De modo similar a lo que ocurre con los Servidores perimetrales, debe configurar la puerta de enlace predeterminada en el adaptador externo solamente. La puerta de enlace predeterminada será la dirección IP del enrutador o firewall externo que dirige el tráfico a Internet. Para el tráfico destinado desde el proxy inverso hacia el adaptador de red interno, deberá usar rutas estáticas persistentes (como el comando enrutar de Windows Server) para todas las subredes que contengan servidores a los que hagan referencia las reglas de publicación web. Establecer una ruta persistente no hace que el equipo se convierta en un enrutador. Si el reenvío IP no está habilitado, el equipo está actuando únicamente para dirigir el tráfico específico destinado a otra red a la interfaz adecuada. Esto establece básicamente dos puertas de enlace: una como la predeterminada que apunta hacia las redes externas y otra para el tráfico destinado a la interfaz interna y a un enrutador u otra red.<br />
> Sin embargo, es posible que no sea necesario crear rutas persistentes para todas las subredes si los enrutadores de su red están configurados para resumir rutas. Cree una ruta persistente a la red en la que está definido el enrutador y use este como puerta de enlace predeterminada. Si no está seguro de cómo está configurada su red y necesita ayuda sobre qué rutas persistentes deben crearse, consulte con los ingenieros de redes de su empresa.<br />
> El proxy inverso debe poder resolver los registros de host (A) DNS del Director interno o Servidor front-end y los FQDN del grupo de servidores del próximo salto que se usan en las reglas de publicación web. Al igual que ocurre con los Servidores perimetrales, por razones de seguridad se recomienda no configurar un proxy inverso para que use un servidor DNS ubicado en la red interna. Esto significa que se necesitan servidores DNS en el perímetro, o bien entradas de archivo HOST en el proxy inverso que resuelva cada uno de estos FQDN para la dirección IP interna de los servidores.


## Para configurar las tarjetas adaptadoras de red en el equipo de proxy inverso

1.  En el servidor de Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2 que se ejecute como el proxy inverso, abra **Cambiar configuración del adaptador** . Para ello, haga clic en **Inicio** , elija **Panel de control** , haga clic en **Centro de redes y recursos compartidos** y, finalmente, haga clic en **Cambiar configuración del adaptador** .

2.  Haga clic con el botón secundario en la conexión de red externa que desea utilizar para la interfaz externa y haga clic en **Propiedades**.

3.  En la página **Propiedades** , haga clic en la pestaña **Redes** , haga clic en **Protocolo de Internet versión 4 (TCP/IPv4)** en la lista **Esta conexión usa los siguientes elementos** y, a continuación, haga clic en **Propiedades** .

4.  En la página **Propiedades del protocolo de Internet (TCP/IP)** , configure las direcciones IP según corresponda para la subred de red a la que está conectado el adaptador de red.
    

    > [!NOTE]
    > Si el proxy inverso ya está siendo utilizado por otras aplicaciones que usan HTTPS/TCP/443, como, por ejemplo, la publicación de Outlook Web Access, deberá agregar otra dirección IP para poder publicar los servicios web de Lync Server 2013 en HTTPS/TCP/443 sin interferir en las escuchas de web y reglas existentes, o bien sustituir el certificado existente por otro que agregue los nuevos nombres FQDN externos al nombre alternativo de sujeto.



5.  Haga clic en **Aceptar** y, a continuación, haga clic en **Aceptar**.

6.  En **Conexiones de red**, haga clic con el botón secundario en la conexión de red interna que desea utilizar para la interfaz interna y, a continuación, haga clic en **Propiedades**.

7.  Repita los pasos del 3 al 5 para configurar la conexión de red interna.

