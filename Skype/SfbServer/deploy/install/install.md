---
title: Instalar Skype Empresarial Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Resumen: Obtenga información sobre cómo preparar su entorno para una instalación de Skype para Business Server. Descargue una versión de prueba gratuita de Skype para Business Server desde el Evaluation de Microsoft center en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: d5c1290e4a7a1beeb2310c69f0c63d7f549e0d76
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21026044"
---
# <a name="install-skype-for-business-server"></a>Instalar Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo preparar su entorno para una instalación de Skype para Business Server. Descargue una versión de prueba gratuita de Skype para Business Server desde el Evaluation de Microsoft center en:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
En este artículo le guiará a través de una instalación de ejemplo de Skype para Business Server. En este artículo no intenta cubrir todos los procedimientos que necesarios para llevar a cabo una completa Skype para la instalación de Business Server. El objetivo es proporcionar procedimientos de ejemplo en una topología estrechamente definida que incluya funcionalidad básica para reunirse y compartir.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Información general del proceso de instalación de Skype para Business Server

Una instalación de Skype para Business Server incluye muchos de los diferentes procedimientos. Los procedimientos que necesita para obtener Skype para Business Server que se ejecuta en el entorno dependen de las características específicas de su entorno. Por ejemplo, si usa Windows Server para el DNS, le interesará conocer el procedimiento de ejemplo para agregar una entrada de DNS. Si usa otro sistema para DNS, será necesario seguir los procedimientos para ese sistema de DNS en concreto. Lo mismo sucede para los demás procedimientos de esta sección.
  
Skype para Business Server está disponible en Standard Edition y Enterprise Edition. La principal diferencia es que Standard Edition no es compatible con las características de alta disponibilidad que se incluyen con Enterprise Edition. 
  
Skype para Business Server es un producto de avanzada y el proceso de instalación exacta depende mucho de las circunstancias específicas. En esta sección le guiará por los pasos generales para instalar el producto. Sin embargo, es posible que cada procedimiento varían en función de su entorno y decisiones de planeación. Por ejemplo, para las organizaciones pequeñas un único servidor, que ejecuta Skype para Business Server Standard Edition podría ser adecuado, mientras que una organización multinacional grande puede tener 50 servidores en ubicaciones de todo el mundo dedicado para el producto.
  
> [!NOTE]
> Para obtener información sobre las actualizaciones acumulativas más recientes, vea [actualizaciones de Skype para Business Server](https://support.microsoft.com/en-us/kb/3061064). Después de instalar la revisión CU1 un administrador debe ejecutar el `Update-CsAdminRole` cmdlet. Este cmdlet se requiere para tener acceso a los nuevos cmdlets GCP a través de PowerShell remoto.
  
> [!IMPORTANT]
> Los procedimientos en esta sección son un ejemplo en el que se asume que ya se han tomado decisiones específicas y que hay un conjunto de requisitos muy definidos. Los procedimientos reales que necesita para instalar Skype para Business Server probablemente será muy diferentes. Use los procedimientos de esta sección como un ejemplo únicamente y no como una guía paso a paso para la instalación de Skype para Business Server en cada entorno. 
  
Obtención de Skype para Business Server copia de seguridad y ejecutar por primera vez implica ocho pasos principales. Debe comprender que los procedimientos de ejemplo de esta sección no son los procedimientos sólo necesarios para la instalación de Skype para Business Server. Los siguientes ocho pasos son simplemente ejemplos que le ayudarán a mejor entender el proceso general y obtener un entorno de trabajo de copia de seguridad básica y ejecución. Se pueden realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se indica en el diagrama. Los ocho pasos son:
  
![Información general del proceso de instalación.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Instalar los requisitos previos de Skype para Business Server](install-prerequisites.md) : instalar los requisitos previos en todos los servidores que componen el Skype de topología de servidores de negocio. Tenga en cuenta que estos requisitos previos no son los mismos para todos los roles. Por ejemplo, los servidores que suministran el rol front-end tienen un conjunto de requisitos previos distinto del de los servidores que proporcionan el rol de director. Consulte la documentación de planeación de requisitos previos para más detalles.
    
- [Crear un recurso compartido de archivos en Skype para Business Server](create-a-file-share.md) : crear un recurso compartido de archivos que se utilizarán los servidores en toda la Skype de topología de servidores de negocio.
    
- [Instalar las herramientas administrativas en Skype para Business Server](install-administrative-tools.md) : las herramientas administrativas de incluyen el generador de topología y Panel de Control. Debe instalar las herramientas administrativas en al menos un servidor en la topología o en una estación de trabajo de administración de 64 bits que ejecuta una versión de sistema operativo de Windows que es compatible con Skype para Business Server.
    
- [Preparar Active Directory para Skype para Business Server](prepare-active-directory.md) : Skype para Business Server trabaja conjuntamente con Active Directory. Debe preparar el dominio de Active Directory para que funcione con Skype para Business Server. Puede hacerlo mediante el Asistente para la implementación, y sólo se realiza una vez para el dominio. Esto es debido a que el proceso crea grupos y modifica el dominio, y debe hacer que sólo una vez.
    
- [Crear registros DNS para Skype para Business Server](create-dns-records.md) : fin de Skype para Business Server funcione correctamente, debe ser un número de configuración DNS en su lugar. De este modo, los clientes sabrán cómo tener acceso a los servicios, mientras que los servidores podrán tener información de los demás servidores. Esta configuración hay que realizarla una sola vez en cada implementación porque, una vez asignada una entrada de DNS, esta estará disponible en todo el dominio.
    
- [Crear y publicar la nueva topología de Skype para Business Server](create-and-publish-new-topology.md) : antes de instalar el Skype para sistema Business Server en cada uno de los servidores de la topología, debe crear una topología y publicarlo. Cuando se publica una topología, se carga información relativa a ella en la base de datos del Almacén de administración central. Si se trata de un grupo de servidores Enterprise Edition, la base de datos del Almacén de administración central se creará la primera vez que se publique una topología nueva. Si es Standard Edition, será necesario ejecutar el proceso Preparar el primer servidor Standard Edition del Asistente para la implementación para poder publicar una topología. Esto prepara a Standard Edition con la instalación de una instancia de SQL Server Express Edition y con la creación del Almacén de administración central.
    
- [Instalar Skype para Business Server en servidores de la topología](install-skype-for-business-server.md) : una vez que la topología se carga en el almacén de Administración Central y Active Directory sabe en qué servidores llevará a cabo las funciones, debe instalar el Skype para sistema Business Server en cada uno de los servidores de la topología.
    
- [Compruebe que la topología en Skype para Business Server](verify-the-topology.md) : una vez que tenga la topología publicada y el Skype para los componentes del sistema de Business Server instalado en cada uno de los servidores de la topología, está listo para comprobar que la topología funciona según lo previsto. Esto incluye la comprobación de que la configuración se propaga fuera a todos los servidores de Active Directory para que todo el dominio sepa que Skype para la empresa está disponible en el dominio.
    

