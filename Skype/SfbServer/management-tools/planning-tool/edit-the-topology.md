---
title: Editar la topología en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Una vez completadas las preguntas iniciales de la entrevista, podrá editar las direcciones IP y el nombre de dominio completo (FQDN) del sitio. Para ello, en la página Topología global, haga doble clic en el sitio que desea editar.
ms.openlocfilehash: 9dcc8f2f69843de5d824ad3df614631ea0d50c20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915062"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>Edit the topology in Skype for Business Server 2015

Una vez completadas las preguntas iniciales de la entrevista, podrá editar las direcciones IP y el nombre de dominio completo (FQDN) del sitio. Para ello, en la página **Topología global**, haga doble clic en el sitio que desea editar.

La herramienta de planeación muestra la topología de sitios para el sitio seleccionado. En la parte inferior de la página del sitio hay cuatro pestañas:

![Herramienta de planeación - Topología del sitio](../../media/Planning_Tool_Site_Topology.png)

- Topología de sitio: la página mostrada actualmente con una descripción general visual de la topología recomendada.

- Diagrama de red perimetral - la página de diagrama de red perimetral es donde el diseñador realiza la mayor parte del trabajo de la herramienta de planeación. El diagrama muestra la configuración de red para una Skype recomendada para la topología empresarial Server 2015, con entradas modificables para IP direcciones y del sistema de nombres de dominio (DNS) y los FQDN de los servidores, grupo de servidores y tanto hardware equilibradores de carga.

- Informe de administración perimetral - el informe de administración perimetral contiene un total de cuatro informes:

     ![Página Informe de administración de servidores perimetrales](../../media/Planning_Tool_Summary_Report.png)

  - Informe de resumen - un informe general de configuración para la configuración de red perimetral. Si modifica los valores de la página **Diagrama de red perimetral** por los valores de TCP/IP y FQDN de la topología que se usarán en la implementación real, esas direcciones y nombres se representarán aquí. De lo contrario, se mostrará el texto predeterminado.

  - Informe de certificado - el informe de certificado se enumerará el nombre de sujeto y nombre alternativo de sujeto para los certificados que son necesarios para la topología.

  - Informe de firewall - del informe de firewall enumera la información necesaria para configurar servidores de seguridad perimetrales en la infraestructura. Esto incluye las direcciones IP (ya sea los valores predeterminados o los modificados), el rol de servidor, el puerto y la IP de origen, el puerto y la IP de destino, el protocolo de transporte, el protocolo de aplicación y las notas relevantes.

  - Informe de DNS - del informe de DNS enumera información relevante para las entradas DNS que debe crear. También se incluye el tipo de registro, el FQDN, la dirección IP y los comentarios necesarios para obtener un funcionamiento correcto.

- Resumen del sitio - el resumen del sitio presenta una visión general de las selecciones realizadas por responder a las preguntas de la entrevista inicial o rellenar los valores de **Diseño de sitios**. También se muestra información sobre la capacidad.

    > [!NOTE]
    > La información de la página Resumen del sitio está personalizada para cada diseño y puede que no contenga todas las secciones o toda la información que se indica aquí.

## <a name="edit-the-network-configuration-diagram"></a>Editar el diagrama de la configuración de red
<a name="Edit_Network_diagram"> </a>

La mayoría del trabajo que hace un diseñador en la Skype para la herramienta de planeación de Business Server 2015 consiste en definir las entradas para las direcciones IP y nombres de dominio completo (FQDN) para las entradas en el diagrama de red. La información que se especifica en esta página se traduce en los informes y otra información contenida en la herramienta de planeación.

![Diagrama de red de la Herramienta de planeación](../../media/Planning_Tool_Network_Diagram.png)

La herramienta de planeación, se crea un diagrama de red con texto predeterminado para las direcciones IP y nombres de dominio completos.

Para editar el diagrama de red y los valores de entrada:

1. Elija una sección de la red en la cual comenzar a trabajar. Por ejemplo, haga doble clic en el texto, **access1.contoso.com**. En el cuadro de diálogo que se abre, escriba el FQDN real del servidor access1.contoso.com y la dirección IP real en lugar de 131.107.155.3.

2. Haga clic en **Aceptar** para guardar las entradas.

3. Continúe con la edición de direcciones IP y FQDN y proporcione direcciones IP virtuales para equilibradores de carga de hardware o entradas de servidores para el equilibrio de carga del Sistema de nombres de dominio (DNS) para servidores incluidos en grupos.

Una característica útil de la herramienta de planeación es que puede asignar de forma gradual un rango de direcciones IP y nombres de host de servidor, en lugar de requerir que el diseñador edite por separado cada servidor de un grupo. Por ejemplo:

1. Haga doble clic en los servidores front-end agrupados. Cuando se abra el cuadro de diálogo, seleccione **¿Desea usar las direcciones IP y el FQDN como puntos de inicio para todos los servidores equivalentes de este clúster?**.

2. Por ejemplo, el valor de inicio para el primer servidor es fe0101.contoso.com y la dirección IP es 192.168.21.122.

3. Escriba fe0.contoso.com en **FQDN de servidor front-end**, escriba 192.168.21.131 en **Dirección IP de servidor front-end** y, después haga clic en **Aceptar**.

4. La característica de incremento automático actualiza todos los servidores del grupo a fe01 hasta fe06 y todas las direcciones IP desde 192.168.21.131 hasta 136.

Una vez completadas todas las modificaciones, guarde la topología. Para ello, siga los siguientes pasos:

Para guardar el diseño de la herramienta de planeación, haga clic en **archivo**y, a continuación, haga clic en **Guardar topología** o **Guardar topología como**. Si aparece el cuadro de diálogo **Guardar herramienta de planeación como**, escriba el nombre del archivo en **Nombre de archivo** y haga clic en **Guardar**.

## <a name="see-also"></a>Vea también
<a name="Edit_Network_diagram"> </a>

[Editing the Design](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
