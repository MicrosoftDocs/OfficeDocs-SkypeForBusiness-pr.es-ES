---
title: Instalar Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Resumen: Aprenda a preparar el entorno para una instalación de Skype empresarial Server. Descargue una prueba gratuita de Skype empresarial Server en el centro de evaluación de Microsoft en https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: b9a89e73f47922493a6d7add320c21b9b9900103
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306779"
---
# <a name="install-skype-for-business-server"></a>Instalar Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo preparar el entorno para una instalación de Skype empresarial Server. Descargue una prueba gratuita de Skype empresarial Server en el centro de evaluación de Microsoft en[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.
  
Este artículo le guiará a través de una instalación de ejemplo de Skype empresarial Server. En este artículo no se trata de tratar todos los procedimientos que necesita para realizar una instalación completa de Skype empresarial Server. El objetivo es proporcionar procedimientos de ejemplo en una topología estrechamente definida que incluya funcionalidad básica para reunirse y compartir.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Información general del proceso de instalación de Skype empresarial Server

Una instalación de Skype empresarial Server incluye muchos procedimientos diferentes. Los procedimientos que necesita para obtener Skype empresarial Server en su entorno dependen de las características específicas de su entorno. Por ejemplo, si usa Windows Server para el DNS, le interesará conocer el procedimiento de ejemplo para agregar una entrada de DNS. Si usa otro sistema para DNS, será necesario seguir los procedimientos para ese sistema de DNS en concreto. Lo mismo sucede para los demás procedimientos de esta sección.
  
Skype empresarial Server está disponible en Standard Edition y Enterprise Edition. La principal diferencia es que Standard Edition no es compatible con las características de alta disponibilidad que se incluyen con Enterprise Edition. 
  
Skype empresarial Server es un producto avanzado, y el proceso de instalación exacto depende de una gran cantidad de circunstancias específicas. Esta sección le guiará a través de los pasos generales para instalar el producto. Sin embargo, cada procedimiento puede ser diferente según el entorno y las decisiones de planeamiento. Por ejemplo, para las pequeñas organizaciones, un único servidor que ejecute Skype empresarial Server Standard Edition puede ser adecuado, mientras que una organización multinacional de gran tamaño puede tener 50 servidores en ubicaciones distintas del mundo dedicado al producto.
  
> [!NOTE]
> Para obtener más información sobre las actualizaciones acumulativas más recientes, consulte [actualizaciones para Skype empresarial Server](https://support.microsoft.com/en-us/kb/3061064). Después de instalar la revisión CU1, un administrador debe ejecutar `Update-CsAdminRole` el cmdlet. Este cmdlet es necesario para acceder a los cmdlets de GCP nuevos en el PowerShell remoto.
  
> [!IMPORTANT]
> Los procedimientos en esta sección son un ejemplo en el que se asume que ya se han tomado decisiones específicas y que hay un conjunto de requisitos muy definidos. Los procedimientos reales que necesita para instalar Skype empresarial Server probablemente sean muy diferentes. Use los procedimientos de esta sección solo como un ejemplo y no como una guía paso a paso para instalar Skype empresarial Server en cada entorno. 
  
Para que Skype empresarial Server se ejecute por primera vez, se necesitan ocho pasos principales. Debe comprender que los procedimientos de ejemplo de esta sección no son los únicos procedimientos necesarios para instalar Skype empresarial Server. Los ocho pasos siguientes son simplemente ejemplos que le ayudarán a comprender mejor el proceso general y a poner en marcha un entorno de trabajo básico. Puede realizar los pasos 1 a 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos 1 a 5, según se indica en el diagrama. Los ocho pasos son:
  
![Información general del proceso de instalación.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Instalar los requisitos previos de Skype empresarial Server](install-prerequisites.md) : Instale los requisitos previos en todos los servidores que componen la topología de servidor de Skype empresarial. Tenga en cuenta que estos requisitos previos no son los mismos para todos los roles. Por ejemplo, los servidores que suministran el rol front-end tienen un conjunto de requisitos previos distinto del de los servidores que proporcionan el rol de director. Consulte la documentación de planeación de requisitos previos para más detalles.
    
- [Crear un recurso compartido de archivos en Skype empresarial Server](create-a-file-share.md) : cree un recurso compartido de archivos que usarán los servidores en toda la topología de Skype empresarial Server.
    
- [Instalar herramientas administrativas en Skype empresarial Server](install-administrative-tools.md) : las herramientas administrativas incluyen el generador de topología y el panel de control. Debe instalar las herramientas administrativas en al menos un servidor de la topología o una estación de trabajo de administración de 64 bits que ejecute una versión de Windows del sistema operativo compatible con Skype empresarial Server.
    
- [Preparar Active Directory para Skype empresarial Server](prepare-active-directory.md) : Skype empresarial Server funciona estrechamente con Active Directory. Debe preparar el dominio de Active Directory para que funcione con Skype empresarial Server. Puede hacerlo mediante el Asistente para la implementación y solo se realiza una vez para el dominio. Esto se debe a que el proceso crea grupos y modifica el dominio, y solo necesita hacerlo una vez.
    
- [Crear registros DNS para Skype empresarial Server](create-dns-records.md) : para que Skype empresarial Server funcione correctamente, debe disponer de una serie de opciones de configuración de DNS. De este modo, los clientes sabrán cómo tener acceso a los servicios, mientras que los servidores podrán tener información de los demás servidores. Esta configuración hay que realizarla una sola vez en cada implementación porque, una vez asignada una entrada de DNS, esta estará disponible en todo el dominio.
    
- [Crear y publicar una nueva topología en Skype empresarial Server](create-and-publish-new-topology.md) : antes de poder instalar el sistema de Skype empresarial Server en cada uno de los servidores de la topología, debe crear una topología y publicarla. Cuando se publica una topología, se carga información relativa a ella en la base de datos del Almacén de administración central. Si se trata de un grupo de servidores Enterprise Edition, la base de datos del Almacén de administración central se creará la primera vez que se publique una topología nueva. Si es Standard Edition, será necesario ejecutar el proceso Preparar el primer servidor Standard Edition del Asistente para la implementación para poder publicar una topología. Esto prepara a Standard Edition con la instalación de una instancia de SQL Server Express Edition y con la creación del Almacén de administración central.
    
- [Instalar Skype empresarial Server en servidores de la topología](install-skype-for-business-server.md) : una vez que se carga la topología en el almacén de administración central y Active Directory sabe qué servidores realizarán qué roles, necesita instalar el sistema de Skype empresarial Server en cada uno de los servidores de la topología.
    
- [Comprobar la topología en Skype empresarial Server](verify-the-topology.md) : después de haber publicado la topología y los componentes del sistema de Skype empresarial Server instalados en cada uno de los servidores de la topología, estará listo para comprobar que la topología funciona de la forma esperada. Esto incluye comprobar que la configuración se propagó a todos los servidores de Active Directory para que todo el dominio sepa que Skype empresarial está disponible en el dominio.
    

