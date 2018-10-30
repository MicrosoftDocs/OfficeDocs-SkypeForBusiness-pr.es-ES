---
title: 'Lync Server 2013: Implementar tipos de direcciones IP en un servidor front-end'
TOCTitle: Implementar tipos de direcciones IP en un servidor front-end
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48276450
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar tipos de direcciones IP en un servidor front-end para Lync Server 2013

 

_**Última modificación del tema:** 2016-07-28_

Con Generador de topologías, siga estos pasos según el procedimiento para implementar tipos de direcciones IP en un Servidor front-end.

## Para implementar los tipos de direcciones IP en un servidor front-end

1.  En **Grupo de servidores front-end Enterprise Edition** , haga clic con el botón secundario dentro de un grupo y seleccione **Editar propiedades** . (También puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción** ).

2.  En el cuadro de diálogo **Editar propiedades** , seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6** , como se muestra en la figura siguiente.
    
    **Cuadro de diálogo Editar propiedades para el grupo de servidores front-end**
    
    ![Cuadro de diálogo Editar propiedades de un servidor front end](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Cuadro de diálogo Editar propiedades de un servidor front end")
    
      - **Use todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.
        

        > [!NOTE]
        > Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).

    
      - **Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, debe introducir un valor para la **dirección IP principal** .
    
      - **Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida debe coincidir con el formato del tipo de dirección seleccionado.
    
      - **Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección debe coincidir con el formato del tipo de dirección seleccionado.

