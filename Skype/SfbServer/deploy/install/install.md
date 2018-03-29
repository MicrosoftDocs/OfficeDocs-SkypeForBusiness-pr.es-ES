---
title: Instalar Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Resumen: Conozca cómo preparar el entorno para la instalación de Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6cb30ef44411705d16ce9175e92a9204d8b09766
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="install-skype-for-business-server-2015"></a>Instalar Skype Empresarial Server 2015
 
**Resumen:** Aprenda a preparar su entorno para la instalación de Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Este artículo le guiará a través de una instalación de ejemplo de Skype para Business Server 2015. Este artículo pretende abarcar todos los procedimientos que debe realizar un completo Skype para instalación del servidor de empresa. El objetivo es proporcionar procedimientos de ejemplo en una topología estrechamente definida que incluya funcionalidad básica para reunirse y compartir.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server-2015"></a>Información general sobre el proceso de instalación de Skype para Business Server 2015

Una instalación de Skype para Business Server incluye muchos procedimientos diferentes. Los procedimientos que necesita para obtener Skype para Business Server que se ejecutan en su entorno dependen de las características específicas de su entorno. Por ejemplo, si usa Windows Server para el DNS, le interesará conocer el procedimiento de ejemplo para agregar una entrada de DNS. Si usa otro sistema para DNS, será necesario seguir los procedimientos para ese sistema de DNS en concreto. Lo mismo sucede para los demás procedimientos de esta sección.
  
Skype para el año 2015 de Business Server está disponible en Standard Edition y Enterprise Edition. La principal diferencia es que Standard Edition no es compatible con las características de alta disponibilidad que se incluyen con Enterprise Edition. 
  
Skype para Business Server es un producto de avanzada y el proceso de instalación exacta depende en gran medida en las circunstancias específicas. Esta sección le guía por los pasos generales para instalar el producto. Sin embargo, cada procedimiento pueden variar dependiendo de su entorno y las decisiones de diseño. Por ejemplo, para las organizaciones pequeñas un solo servidor, ejecutando Skype para 2015 Business Server Standard Edition puede ser apropiada, una gran organización multinacional podría tener 50 servidores en ubicaciones alrededor del mundo dedicadas al producto.
  
> [!NOTE]
> Para obtener información sobre las actualizaciones acumulativas más recientes, vea [versiones de Skype para Business Server 2015](https://support.microsoft.com/en-us/kb/3061064). Después de instalar la revisión CU1, un administrador debe ejecutar la `Update-CsAdminRole` cmdlet. Este cmdlet es necesario para tener acceso a los nuevos cmdlets GCP sobre PowerShell remoto.
  
> [!IMPORTANT]
> Los procedimientos en esta sección son un ejemplo en el que se asume que ya se han tomado decisiones específicas y que hay un conjunto de requisitos muy definidos. Los procedimientos reales que debe instalar Skype para Business Server probablemente será muy diferentes. Utilice los procedimientos de esta sección como un ejemplo únicamente y no como una guía paso a paso para instalar Skype para Business Server en cada entorno. 
  
Obtener Skype para Business Server y ejecutar por primera vez implica ocho pasos principales. Debe comprender que los procedimientos de ejemplo de esta sección no son el único procedimientos necesarios para instalar Skype para Business Server. Los siguientes ocho pasos son simplemente ejemplos que le ayudarán a mejor entienden el proceso general y obtén un entorno de trabajo básico y ejecución. Puede realizar los pasos 1 a 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después los pasos del 1 al 5, tal como se indica en el diagrama. Los ocho pasos son:
  
![Información general del proceso de instalación.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Instalar los requisitos previos para Skype para Business Server 2015](install-prerequisites.md) : instalar los requisitos previos en todos los servidores que componen el Skype para la topología de servidores de empresa. Tenga en cuenta que estos requisitos previos no son los mismos para todos los roles. Por ejemplo, los servidores que suministran el rol front-end tienen un conjunto de requisitos previos distinto del de los servidores que proporcionan el rol de director. Consulte la documentación de planeación de requisitos previos para más detalles.
    
- [Crear un recurso compartido de archivo en Skype para Business Server 2015](create-a-file-share.md) : crear un recurso compartido de archivo que se utilizará por servidores en todo el Skype para la topología de servidores de empresa.
    
- [Instalar las herramientas administrativas en Skype para Business Server 2015](install-administrative-tools.md) : incluyen las herramientas administrativas de Panel de Control y el generador de topología. Debe instalar las herramientas administrativas en al menos un servidor en la topología o en una estación de trabajo de administración de 64 bits que ejecuta una versión de sistema operativo de Windows que es compatible con Skype para Business Server.
    
- [Preparar Active Directory para Skype para Business Server 2015](prepare-active-directory.md) : Skype para Business Server trabaja en estrecha colaboración con Active Directory. Debe preparar el dominio de Active Directory para trabajar con Skype para Business Server. Puede hacerlo mediante el Asistente para implementación y sólo se realiza una vez para el dominio. Esto es porque el proceso crea grupos y modifica el dominio, y debe hacer que sólo una vez.
    
- [Registros DNS crear Skype para Business Server 2015](create-dns-records.md) : fin de Skype para Business Server funcione correctamente, debe ser un número de parámetros de DNS en su lugar. De este modo, los clientes sabrán cómo tener acceso a los servicios, mientras que los servidores podrán tener información de los demás servidores. Esta configuración hay que realizarla una sola vez en cada implementación porque, una vez asignada una entrada de DNS, esta estará disponible en todo el dominio.
    
- [Crear y publicar la nueva topología en Skype para Business Server 2015](create-and-publish-new-topology.md) : antes de instalar el Skype para sistema Business Server en cada uno de los servidores de la topología, debe crear una topología y publicarlo. Cuando se publica una topología, se carga información relativa a ella en la base de datos del Almacén de administración central. Si se trata de un grupo de servidores Enterprise Edition, la base de datos del Almacén de administración central se creará la primera vez que se publique una topología nueva. Si es Standard Edition, será necesario ejecutar el proceso Preparar el primer servidor Standard Edition del Asistente para la implementación para poder publicar una topología. Esto prepara a Standard Edition con la instalación de una instancia de SQL Server Express Edition y con la creación del Almacén de administración central.
    
- [Instalar Skype para Business Server 2015 en servidores de la topología](install-skype-for-business-server.md) : una vez que la topología se carga en el almacén de Administración Central y Active Directory sabe qué servidores realizan los roles, necesitará instalar el Skype para sistema Business Server en cada uno de los servidores de la topología.
    
- [Comprobar la topología de Skype para Business Server 2015](verify-the-topology.md) : una vez que la topología publicada y el Skype para componentes del sistema de Business Server instalado en cada uno de los servidores de la topología, esté preparado para comprobar que la topología funciona como se esperaba . Esto incluye la comprobación de que la configuración propagada a todos los servidores de Active Directory para que sepa de todo el dominio que Skype para empresas está disponible en el dominio.
    

