---
title: Edición del diagrama de la configuración de red
TOCTitle: Edición del diagrama de la configuración de red
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558643(v=OCS.15)
ms:contentKeyID: 52061677
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Edición del diagrama de la configuración de red

 

_**Última modificación del tema:** 2013-02-21_

La mayor parte del trabajo que realiza el diseñador en Lync Server 2013, herramienta de planeación consiste en definir las entradas para las direcciones IP y los nombres de dominio completos (FQDN) para las entradas del diagrama de red. La información especificada en esta página se propaga en los informes y en otra información incluida en la Herramienta de planeación.

![Diagrama de red de la Herramienta de planeación](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Diagrama de red de la Herramienta de planeación")

La Herramienta de planeación crea un diagrama de red con texto predeterminado para las direcciones IP y los FQDN.

Para editar el diagrama de red y los valores de entrada:

1.  Elija una sección de la red en la cual comenzar a trabajar. Por ejemplo, haga doble clic en el texto **access1.contoso.com**. En el cuadro de diálogo que se abre, escriba el FQDN real del servidor access1.contoso.com y la dirección IP real en lugar de 131.107.155.3.

2.  Haga clic en **Aceptar** para guardar las entradas.

3.  Continúe con la edición de direcciones IP y FQDN y proporcione direcciones IP virtuales para equilibradores de carga de hardware o entradas de servidores para el equilibrio de carga del Sistema de nombres de dominio (DNS) para servidores incluidos en grupos.

Una característica útil de la herramienta de planeación es que puede asignar de forma gradual un rango de direcciones IP y nombres de host de servidor, en lugar de requerir que el diseñador edite por separado cada servidor de un grupo. Por ejemplo:

1.  Haga doble clic en los servidores front-end agrupados. Cuando se abra el cuadro de diálogo, seleccione **¿Desea usar las direcciones IP y el FQDN como puntos de inicio para todos los servidores equivalentes de este clúster?**.

2.  Por ejemplo, el valor de inicio para el primer servidor es fe0101.contoso.com y la dirección IP es 192.168.21.122.

3.  Escriba **fe0.contoso.com** en **FQDN de servidor front-end**, **192.168.21.131** en **Dirección IP de servidor front-end** y haga clic en **Aceptar**.

4.  La característica de incremento automático actualiza todos los servidores del grupo a fe01 hasta fe06 y todas las direcciones IP desde 192.168.21.131 hasta 136.

Una vez completadas todas las modificaciones, guarde la topología. Para ello, siga los siguientes pasos:

Para guardar el diseño de Herramienta de planeación, haga clic en **Archivo** y, a continuación, haga clic en **Guardar topología** o **Guardar topología como**. Si aparece el cuadro de diálogo **Guardar herramienta de planeación como**, escriba el nombre del archivo en **Nombre de archivo** y haga clic en **Guardar**.

## Vea también

#### Conceptos

[Edición del diseño en Lync Server 2013](lync-server-2013-editing-the-design.md)

