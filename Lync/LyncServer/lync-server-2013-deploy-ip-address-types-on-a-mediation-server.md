---
title: "Lync Server 2013: Implementar tipos de dirección IP en servidor de mediación"
TOCTitle: Implementar tipos de dirección IP en un servidor de mediación
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48275529
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar tipos de dirección IP en un servidor de mediación para Lync Server 2013

 

_**Última modificación del tema:** 2016-07-28_

Con Generador de topologías, siga estos pasos según el procedimiento para implementar tipos de direcciones IP en un Servidor de mediación.

## Para implementar tipos de direcciones IP en un servidor de mediación

  - En el Generador de topologías, en **Grupos de servidores de mediación** , haga clic con el botón secundario en el servidor dentro de un grupo y seleccione **Editar propiedades** (otra opción es seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción** ).

  - En el cuadro de diálogo **Editar propiedades** , seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6** , como se muestra en la figura siguiente.
    
    **Cuadro de diálogo Editar propiedades para el grupo Servidor de mediación**
    
    ![Página de propiedades generales de Lync Server con FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Página de propiedades generales de Lync Server con FQDN")
    
      - **Use todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.
        

        > [!NOTE]
        > Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).

    
      - **Limitar el uso del servicio a las direcciones especificadas**. Seleccione esta opción para especificar una dirección concreta para usarla en el nuevo servidor. Si selecciona esta opción, debe indicar un valor de dirección IP principal.
    
      - **Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida debe coincidir con el formato del tipo de dirección seleccionado.
    
      - **Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección debe coincidir con el formato del tipo de dirección seleccionado.
        

        > [!NOTE]
        > La instalación de tarjetas de interfaz de red (NIC) adicionales para admitir la configuración de dirección IP RTC para Lync Server 2013 no se admite. Para más información sobre las configuraciones de NIC admitidas en Lync Server 2013, vea <A href="lync-server-2013-server-hardware-platforms.md">Plataformas de hardware de servidor para Lync Server 2013</A>.


