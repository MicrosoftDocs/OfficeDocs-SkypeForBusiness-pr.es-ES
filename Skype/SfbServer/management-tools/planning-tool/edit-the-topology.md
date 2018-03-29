---
title: Editar la topología en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Una vez completadas las preguntas iniciales de la entrevista, podrá editar las direcciones IP y el nombre de dominio completo (FQDN) del sitio. Para ello, en la página de la topología Global del sistema, haga doble clic en el sitio que desea editar.
ms.openlocfilehash: 7de778c9aed8594df4fc70f9a6635bd0c21c6db4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>Editar la topología en Skype Empresarial Server 2015
 
Una vez completadas las preguntas iniciales de la entrevista, podrá editar las direcciones IP y el nombre de dominio completo (FQDN) del sitio. Para ello, en la página **Topología global**, haga doble clic en el sitio que desea editar.
  
La herramienta de planeación muestra la topología de sitios para el sitio seleccionado. En la parte inferior de la página del sitio hay cuatro pestañas:
  
![Herramienta de planeación - Topología del sitio](../../media/Planning_Tool_Site_Topology.png)
  
- Topología de sitio: la página mostrada actualmente con un resumen visual de la topología recomendada.
    
- Diagrama de red de borde - la página de diagrama de red de borde es donde el diseñador realiza la mayor parte del trabajo de la herramienta de planeación. El diagrama muestra la configuración de red de un Skype para Business Server 2015 topología recomendada, con entradas editables para IP y direcciones FQDN de los servidores, el grupo y tanto hardware y sistema de nombres de dominio (DNS) equilibradores de carga.
    
- Informe de administración de borde - el informe de administración de borde contiene un total de cuatro informes:
    
     ![Página Informe de administración de servidores perimetrales](../../media/Planning_Tool_Summary_Report.png)
  
  - Informe Resumen: un informe general de configuración para la configuración de la red perimetral. Si modifica los valores de la página **Diagrama de red perimetral** por los valores de TCP/IP y FQDN de la topología que se usarán en la implementación real, esas direcciones y nombres se representarán aquí. De lo contrario, se mostrará el texto predeterminado.
    
  - Informe certificado - el informe certificado mostrará el nombre del sujeto y los nombres alternativos de asunto de los certificados que se requieren para la topología.
    
  - Informe de Firewall - el informe del servidor de seguridad muestra información necesaria para configurar servidores de seguridad perimetrales en la infraestructura. Esto incluye las direcciones IP (ya sea los valores predeterminados o los modificados), el rol de servidor, el puerto y la IP de origen, el puerto y la IP de destino, el protocolo de transporte, el protocolo de aplicación y las notas relevantes.
    
  - Informe DNS - el informe DNS muestra información pertinente para las entradas DNS que debe crear. También se incluye el tipo de registro, el FQDN, la dirección IP y los comentarios necesarios para obtener un funcionamiento correcto.
    
- Resumen del sitio - el resumen del sitio presenta una visión general de las selecciones que ha realizado por responder a las preguntas de la entrevista inicial o rellenar los valores de **Diseño de sitios**. También se muestra información sobre la capacidad. 
    
    > [!NOTE]
    > La información de la página Resumen del sitio está personalizada para cada diseño y puede que no contenga todas las secciones o toda la información que se indica aquí. 
  
## <a name="edit-the-network-configuration-diagram"></a>Editar el diagrama de la configuración de red
<a name="Edit_Network_diagram"> </a>

La mayor parte del trabajo que realiza un diseñador en el Skype para la herramienta de planeación de 2015 Business Server consiste en definir las entradas para las direcciones IP y nombres de dominio completo (FQDN) para las entradas en el diagrama de red. La información que se especifica en esta página se traduce en los informes y otra información contenida en la herramienta de planeación. 
  
![Diagrama de red de la Herramienta de planeación](../../media/Planning_Tool_Network_Diagram.png)
  
La herramienta de planeación, se crea un diagrama de red con texto predeterminado de direcciones IP y nombres de dominio completos. 
  
Para editar el diagrama de red y los valores de entrada:
  
1. Elija una sección de la red en la cual comenzar a trabajar. Por ejemplo, haga doble clic en el texto, **access1.contoso.com**. En el cuadro de diálogo que se abre, escriba el FQDN real del servidor access1.contoso.com y la dirección IP real en lugar de 131.107.155.3.
    
2. Haga clic en **Aceptar** para guardar las entradas.
    
3. Continúe con la edición de direcciones IP y FQDN y proporcione direcciones IP virtuales para equilibradores de carga de hardware o entradas de servidores para el equilibrio de carga del Sistema de nombres de dominio (DNS) para servidores incluidos en grupos.
    
Una característica útil de la herramienta de planeación es que puede asignar de forma gradual un rango de direcciones IP y nombres de host de servidor, en lugar de requerir que el diseñador edite por separado cada servidor de un grupo. Por ejemplo:
  
1. Haga doble clic en los servidores front-end agrupados. Cuando se abra el cuadro de diálogo, seleccione **¿Desea usar las direcciones IP y el FQDN como puntos de inicio para todos los servidores equivalentes de este clúster?**. 
    
2. Por ejemplo, el valor de inicio para el primer servidor es fe0101.contoso.com y la dirección IP es 192.168.21.122.
    
3. Escriba fe0.contoso.com en el **Front End servidor FQDN**, escriba 192.168.21.131 en la **dirección IP del servidor de Front End**y, a continuación, haga clic en **Aceptar**.
    
4. La característica de incremento automático actualiza todos los servidores del grupo a fe01 hasta fe06 y todas las direcciones IP desde 192.168.21.131 hasta 136.
    
Una vez completadas todas las modificaciones, guarde la topología. Para ello, siga los siguientes pasos: 
  
Para guardar el diseño de la herramienta de planeación, haga clic en **archivo**y, a continuación, haga clic en **Topología guardar** o **Guardar la topología como**. Si aparece el cuadro de diálogo **Guardar herramienta de planeación como**, escriba el nombre del archivo en **Nombre de archivo** y haga clic en **Guardar**. 
  
## <a name="see-also"></a>Vea también
<a name="Edit_Network_diagram"> </a>

#### 

[Edición del diseño](http://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)

