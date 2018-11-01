---
title: 'Lync Server 2013: Configurar DNS para admitir servidores perimetrales'
TOCTitle: Configurar DNS para admitir servidores perimetrales
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48276066
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar DNS para admitir servidores perimetrales en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-15_

Debe configurar registros DNS (Sistema de nombres de dominio) para las interfaces perimetrales interna y externa, incluidas las interfaces de proxy inverso y servidor perimetral. De modo predeterminado, los servidores perimetrales no se unen a un dominio y no dispondrán de un nombre de dominio completo (FQDN). Se menciona al servidor perimetral solo por el nombre corto (equipo), no por el nombre de dominio completo. Sin embargo, Generador de topologías utiliza el FQDN en vez de nombres cortos. El nombre del servidor perimetral debe coincidir con el FQDN utilizado por el Generador de topologías. Para ello, debe definir un sufijo DNS que, combinado con el nombre del equipo, resulte en el FQDN esperado. Utilice el procedimiento siguiente en "Añadir el sufijo DNS al nombre del equipo en un servidor perimetral que no se ha unido a un dominio" para añadir el sufijo DNS al nombre del equipo.


> [!NOTE]
> De modo predeterminado, el DNS utiliza un algoritmo round robin para rotar el orden de los datos del registro del recurso devueltos en las respuestas a las consultas en las que existen varios registros de recursos del mismo tipo para los nombres de domino DNS consultados. El equilibrador de carga de DNS de Lync Server 2013 depende del round robin del DNS como parte del mecanismo de equilibrio de carga de DNS. Compruebe que la configuración de round robin no se haya deshabilitado. Si utiliza un servidor DNS que no se ejecuta en el sistema operativo Windows, compruebe que el orden de registros del recurso round robin esté activado.



Utilice el procedimiento siguiente en “ **Creación de un registro DNS SRV** ” para crear y comprobar todos los registros SRV de DNS. Utilice el procedimiento en “ **Creación de un registro A de DNS** ” para definir los registros A de DNS necesarios para el acceso de usuarios externos. Para confirmar que los registros están configurados y funcionan correctamente, consulte “ **Verificación de un registro DNS** ” en este tema. Para obtener información sobre los registros que son necesarios para permitir el acceso de usuarios externos, consulte [Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

## Para configurar el Sistema de nombres de dominio (DNS), debe configurar registros DNS y un sufijo DNS para el nombre de equipo de cada servidor perimetral que no esté unido a un dominio.

1.  En el equipo, haga clic en **Inicio** , haga clic con el botón secundario en **Equipo** y, a continuación, haga clic en **Propiedades** .

2.  En **Configuración del nombre del equipo, dominio y grupo de trabajo** , haga clic en **Cambiar configuración** .

3.  En la pestaña **Nombre del equipo** , haga clic en **Cambiar** .

4.  En **Cambios del nombre del equipo/dominio** , haga clic en **Más** .

5.  En **Sufijo DNS y nombre NetBIOS del equipo** , en **Sufijo DNS principal de este equipo** , escriba el nombre de su dominio interno (por ejemplo, corp.contoso.com), y haga clic en **Aceptar** tres veces.

6.  Reinicie el equipo.

## Para crear un registro SRV de DNS

1.  En el servidor DNS pertinente, haga clic en **Inicio** , en **Panel de control** , en **Herramientas administrativas** y, a continuación, en **DNS** .
    
    > [!IMPORTANT]  
    > Se debe configurar el DNS para que haya: 1) entradas de DNS externas para búsquedas de DNS externas realizadas por usuarios remotos y socios federados; 2) entradas para búsquedas de DNS que puedan utilizar los servidores perimetrales en la red perimetral (también conocida como red perimetral y subred filtrada), incluidos los registros A para los servidores internos que ejecutan Lync Server 2013 y 3) entradas de DNS internas para búsquedas realizadas por clientes internos y servidores que ejecutan Lync Server 2013.
    


2.  En el árbol de la consola de su dominio SIP, expanda **Zonas de búsqueda directa** y, a continuación, haga clic con el botón secundario en el dominio en el que el Lync Server 2013 está instalado.

3.  Haga clic en **Otros nuevos registros** .

4.  En **Seleccione el tipo de registro del recurso** , escriba **Ubicación de servicio (SRV)** y, a continuación, haga clic en **Crear registro** .

5.  Suministre toda la información necesaria para el registro SRV de DNS.

## Para crear un registro A de DNS

1.  En el servidor DNS, haga clic en **Inicio** , en **Panel de control** , en **Herramientas administrativas** y, a continuación, en **DNS** .

2.  En el árbol de la consola del dominio SIP, expanda **Zonas de búsqueda directa** y, a continuación, haga clic con el botón secundario en el dominio en el que el Lync Server 2013 está instalado.

3.  Haga clic en **Host nuevo (A)** .

4.  Suministre toda la información necesaria para el registro SRV de DNS.

## Para comprobar un registro DNS

1.  Inicie sesión en un equipo cliente en el dominio.

2.  Haga clic en **Inicio** y en **Ejecutar** .

3.  En el símbolo del sistema, ejecute el comando siguiente:
    
        nslookup <FQDN edge interface>

4.  Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.

## Vea también

#### Tareas

[Crear un registro DNS SRV para la integración con mensajería unificada (UM) hospedada de Exchange](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  

#### Conceptos

[Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

