---
title: "Definir un servidor o aplicación de sucursal con funciones de supervivencia"
TOCTitle: Definir un servidor o aplicación de sucursal con funciones de supervivencia
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48274650
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir un servidor o aplicación de sucursal con funciones de supervivencia en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-07_

Lleve a cabo este procedimiento en el sitio central en caso de que no haya definido la aplicación o el servidor de sucursal con funciones de supervivencia tras agregarlos a la topología.

## Para definir una Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia

1.  Haga clic en **Inicio**, **Todos los programas** y **Microsoft Lync Server 2013**, y después haga clic en **Lync ServerGenerador de topologías**.

2.  En el árbol de la consola, expanda sucesivamente el sitio central, **Sucursales** y el nombre de la sucursal en la que vaya a implementar la Aplicación de sucursal con funciones de supervivencia o el Servidor de sucursal con funciones de supervivencia.

3.  Haga clic con el botón secundario en **Aplicaciones de sucursal con funciones de supervivencia** y después haga clic en **Nueva Aplicación de sucursal con funciones de supervivencia**.
    
    > [!IMPORTANT]  
    > En <strong>Aplicaciones de sucursal con funciones de supervivencia</strong> se definen tanto los Servidores de sucursal con funciones de supervivencia como las Aplicaciones de sucursal con funciones de supervivencia.
    


4.  En el cuadro de diálogo **Definir Aplicación de sucursal con funciones de supervivencia**, haga clic en **FQDN**, escriba el nombre de dominio completo (FQDN) de la Aplicación de sucursal con funciones de supervivencia o del Servidor de sucursal con funciones de supervivencia que va a implementar en la sucursal y haga clic en **Siguiente**.
    
    > [!IMPORTANT]  
    > Si está definiendo una Aplicación de sucursal con funciones de supervivencia, el nombre que especifique en <strong>FQDN</strong> debe ser el mismo que el FQDN de Aplicación de sucursal con funciones de supervivencia que hay asignado al atributo <strong>servicePrincipalName</strong>. Para más información detallada, consulte <a href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013</a>.
    


5.  Haga clic en **Grupo de servidores front-end**, haga clic en el servidor front-end (grupo de servidores Servicios de usuario) del sitio central al que la Aplicación de sucursal con funciones de supervivencia o el Servidor de sucursal con funciones de supervivencia se va a conectar y luego haga clic en **Siguiente**.

6.  Haga clic en **Servidor perimetral**, haga clic en el grupo de servidores perimetrales al que la Aplicación de sucursal con funciones de supervivencia o el Servidor de sucursal con funciones de supervivencia va a conectarse para proveer de conectividad RTC a los usuarios remotos de la sucursal y después haga clic en **Siguiente**.

7.  Haga clic en **FQDN de puerta de enlace o dirección IP** y después escriba el FQDN o la dirección IP del nivel de puerta de enlace al que se asocia la Aplicación de sucursal con funciones de supervivencia o el Servidor de sucursal con funciones de supervivencia para enrutar las llamadas RTC entrantes o realizadas.
    
    > [!IMPORTANT]  
    > Si está definiendo una Aplicación de sucursal con funciones de supervivencia, se trata de la puerta de enlace a la que se conectará el servidor de mediación de Aplicación de sucursal con funciones de supervivencia para conectividad de red telefónica conmutada (RTC).
    


8.  Haga clic en **Puerto de escucha para puerta de enlace IP/RTC** y acepte el puerto predeterminado.

9.  En **Protocolo de transporte SIP**, haga clic en el protocolo de transporte que la Aplicación de sucursal con funciones de supervivencia o el Servidor de sucursal con funciones de supervivencia va a usar y haga clic en **Finalizar**.
    

    > [!NOTE]
    > Por motivos de seguridad, se recomienda encarecidamente usar Seguridad de la capa de transporte (TLS). Si está definiendo una Aplicación de sucursal con funciones de supervivencia, consulte la documentación del proveedor de Aplicación de sucursal con funciones de supervivencia para confirmar que Aplicación de sucursal con funciones de supervivencia admite el protocolo TLS.



10. En el árbol de la consola, haga clic con el botón secundario en la nueva aplicación o servidor de sucursal con funciones de supervivencia, haga clic en **Topología** y después haga clic en **Publicar**.

**Siguiente paso**: [Implementar una aplicación o servidor de sucursal con funciones de supervivencia con Lync Server 2013 - Tarea en el sitio de sucursal](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

