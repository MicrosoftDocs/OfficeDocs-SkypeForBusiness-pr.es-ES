---
title: Editar la topología en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Después de completar las preguntas iniciales de la entrevista, puede editar el nombre de dominio completo (FQDN) y las direcciones IP del sitio. Para ello, en la página Topología global, haga clic con el botón secundario en el sitio que desea editar.
ms.openlocfilehash: ba18070b21494028d31b4167ab92a622794c5e51
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834890"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>Editar la topología en Skype Empresarial Server 2015

Después de completar las preguntas iniciales de la entrevista, puede editar el nombre de dominio completo (FQDN) y las direcciones IP del sitio. Para ello, en la página **Topología global**, haga clic con el botón secundario en el sitio que desea editar.

La Herramienta de planeación muestra la topología del sitio seleccionado. En la parte inferior de la página del sitio hay cuatro pestañas:

![Topología de sitio de la herramienta de planeación](../../media/Planning_Tool_Site_Topology.png)

- Topología de sitio: página que se muestra actualmente con información general visual de la topología según se recomienda.

- Diagrama de red perimetral: la página Diagrama de red perimetral es donde el diseñador realiza la mayor parte del trabajo en la Herramienta de planeación. El diagrama muestra la configuración de red para una topología recomendada de Skype Empresarial Server 2015, con entradas editables para direcciones IP y FQDN para servidores, grupos de servidores y equilibradores de carga de hardware y sistema de nombres de dominio (DNS).

- Informe de administración perimetral: el informe de administración perimetral contiene un total de cuatro informes:

     ![Página informe de administración perimetral](../../media/Planning_Tool_Summary_Report.png)

  - Informe de resumen: informe general de la configuración de la red perimetral. Si edita los  valores de la página Diagrama de red perimetral con los valores TCP/IP y FQDN de la topología que se usarán en la implementación real, esas direcciones y nombres se representarán aquí. De lo contrario, aparecerá el texto predeterminado.

  - Informe de certificados: el informe de certificados enumerará el nombre de sujeto y los nombres alternativos de sujeto de los certificados necesarios para la topología.

  - Informe de firewall: el informe de firewall muestra la información necesaria para configurar firewalls perimetrales en la infraestructura. Esto incluye las direcciones IP (los valores predeterminados o modificados), el rol de servidor, la IP y el puerto de origen, la DIRECCIÓN IP y el puerto de destino, el protocolo de transporte, el protocolo de aplicación y las notas relevantes.

  - Informe de DNS: el informe de DNS muestra información relevante para las entradas DNS que debe crear. También se incluye el tipo de registro, el FQDN, la dirección IP y los comentarios necesarios para que obtener un funcionamiento correcto.

- Resumen del sitio: el resumen del sitio presenta una introducción a las selecciones realizadas respondiendo a las preguntas iniciales de la entrevista o rellenando los valores de Los sitios **de diseño.** También se presenta información de capacidad.

    > [!NOTE]
    > La información de la página Resumen del sitio está personalizada para cada diseño y puede que no contenga todas las secciones o toda la información que se indica aquí.

## <a name="edit-the-network-configuration-diagram"></a>Editar el diagrama de configuración de red
<a name="Edit_Network_diagram"> </a>

La mayor parte del trabajo que realiza un diseñador en la Herramienta de planeación de Skype Empresarial Server 2015 consiste en definir las entradas para las direcciones IP y los nombres de dominio completos (FQDN) para las entradas del diagrama de red. La información que se introduce en esta página se transmite a los informes y a otra información contenida en la Herramienta de planeación.

![Diagrama de la red de la herramienta de planeación](../../media/Planning_Tool_Network_Diagram.png)

La Herramienta de planeación crea un diagrama de red con texto predeterminado para direcciones IP y FQDN.

Para editar el diagrama de red y los valores de entrada:

1. Seleccione una sección de la red en la que desee comenzar a trabajar. Por ejemplo, haga doble clic en el texto, **access1.contoso.com**. En el cuadro de diálogo que se abre, escriba el FQDN real del servidor access1.contoso.com y la dirección IP real, en reemplazo de 131.107.155.3.

2. Haga clic en **Aceptar** para guardar las entradas.

3. Continúe con la edición de direcciones IP y FQDN y proporcione direcciones IP virtuales para equilibradores de carga de hardware o entradas de servidores para el equilibrio de carga del Sistema de nombres de dominio (DNS) para servidores incluidos en grupos.

Una característica útil de la herramienta de planeación es que puede asignar de forma gradual un rango de direcciones IP y nombres de host de servidor, en lugar de requerir que el diseñador edite por separado cada servidor de un grupo. Por ejemplo:

1. Haga doble clic en los servidores front-end agrupados. Cuando se abra el cuadro de diálogo, seleccione **¿Desea usar las direcciones IP y el FQDN como puntos de inicio para todos los servidores equivalentes de este clúster?**.

2. Por ejemplo, el valor inicial del primer servidor es fe0101.contoso.com y una dirección IP de 192.168.21.122.

3. Escriba fe0.contoso.com nombre de dominio completo del servidor front-end **,** escriba 192.168.21.131 en la dirección IP del servidor **front-end** y, a continuación, haga clic en **Aceptar**.

4. La característica de incremento automático actualiza todos los servidores del grupo a fe01 a fe06 y todas las direcciones IP de 192.168.21.131 a 136.

Después de completar todas las modificaciones, guarde la topología siguiendo estos pasos:

Para guardar el diseño de la Herramienta de planeación, **haga** clic en Archivo y, a continuación, haga clic en Guardar **topología** o Guardar **topología como**. Si aparece el cuadro de diálogo **Guardar herramienta de planeación como**, escriba el nombre del archivo en **Nombre de archivo** y haga clic en **Guardar**.

## <a name="see-also"></a>Vea también
<a name="Edit_Network_diagram"> </a>

[Edición del diseño](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
