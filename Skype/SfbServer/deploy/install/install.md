---
title: Instalar Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 'Resumen: Obtenga información sobre cómo preparar el entorno para una instalación de Skype empresarial Server. Descargue una versión de prueba gratuita de Skype empresarial Server del centro de evaluación de Microsoft https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serveren:.'
ms.openlocfilehash: e33e773abf25be92c163de259af0c3f47e0b1783
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042387"
---
# <a name="install-skype-for-business-server"></a>Instalar Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo preparar el entorno para una instalación de Skype empresarial Server. Descargue una versión de prueba gratuita de Skype empresarial Server del centro de evaluación de Microsoft[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)en:.
  
Este artículo le guiará a través de una instalación de ejemplo de Skype empresarial Server. Este artículo no trata de tratar todos los procedimientos necesarios para realizar una instalación completa de Skype empresarial Server. El objetivo es proporcionar procedimientos de ejemplo en una topología definida de forma estrecha que incluya la funcionalidad básica de reunirse y compartir.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Información general sobre el proceso de instalación de Skype empresarial Server

Una instalación de Skype empresarial Server incluye muchos procedimientos distintos. Los procedimientos que necesita para obtener Skype empresarial Server que se ejecuta en su entorno dependen de las características específicas de su entorno. Por ejemplo, si usa Windows Server para DNS, se beneficiará del procedimiento de ejemplo para agregar una entrada DNS. Si usa otro sistema para DNS, debe seguir los procedimientos de su sistema DNS en particular. Esto es válido para muchos de los procedimientos de esta sección.
  
Skype empresarial Server está disponible en Standard Edition y Enterprise Edition. La principal diferencia es que Standard Edition no es compatible con las características de alta disponibilidad que se incluyen con Enterprise Edition. 
  
Skype empresarial Server es un producto avanzado y el proceso de instalación exacto depende de una gran cantidad de circunstancias específicas. Esta sección le guiará por los pasos generales para instalar el producto. Sin embargo, cada procedimiento puede variar según el entorno y las decisiones de planeación. Por ejemplo, para las organizaciones pequeñas un solo servidor, ejecutar Skype empresarial Server Standard Edition podría ser adecuado, mientras que una organización multinacional de gran tamaño puede tener 50 servidores en ubicaciones alrededor del mundo dedicado al producto.
  
> [!NOTE]
> Para obtener información sobre las actualizaciones acumulativas más recientes, consulte [actualizaciones para Skype empresarial Server](https://support.microsoft.com/kb/3061064). Después de instalar la revisión CU1, un administrador debe ejecutar `Update-CsAdminRole` el cmdlet. Este cmdlet es necesario para acceder a los cmdlets de GCP nuevos a través de PowerShell remoto.
  
> [!IMPORTANT]
> Los procedimientos de esta sección sirven como un ejemplo de uso de un conjunto de requisitos muy definidos y asumen que ya se han tomado decisiones específicas. Los procedimientos reales que necesita para instalar Skype empresarial Server probablemente serán muy diferentes. Use los procedimientos de esta sección solo como un ejemplo y no como una guía paso a paso para instalar Skype empresarial Server en cada entorno. 
  
La puesta en marcha de Skype empresarial Server por primera vez implica ocho pasos principales. Debe comprender que los procedimientos de ejemplo de esta sección no son los únicos procedimientos necesarios para instalar Skype empresarial Server. Los ocho pasos siguientes son simplemente ejemplos que le ayudarán a comprender mejor el proceso general y a poner en marcha un entorno de trabajo básico. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos del 1 al 5, tal y como se describe en el diagrama. Los ocho pasos son los siguientes:
  
![Información general sobre el proceso de instalación.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Instalar los requisitos previos de Skype empresarial Server](install-prerequisites.md) : Instale los requisitos previos en todos los servidores que componen la topología de Skype empresarial Server. Tenga en cuenta que los requisitos previos no son los mismos para todos los roles. Por ejemplo, los servidores que proporcionan el rol de front-end tienen un conjunto de requisitos previos, y los servidores que proporcionan un rol de Director tienen un conjunto de requisitos previos diferente. Consulte la documentación de planeación de requisitos previos para obtener más información.
    
- [Cree un recurso compartido de archivos en Skype empresarial Server](create-a-file-share.md) : cree un recurso compartido de archivos que usarán los servidores en toda la topología de Skype empresarial Server.
    
- [Instalar herramientas administrativas en Skype empresarial Server](install-administrative-tools.md) : las herramientas administrativas incluyen el generador de topologías y el panel de control. Debe instalar las herramientas administrativas en al menos un servidor de la topología o una estación de trabajo de administración de 64 bits que ejecute una versión de sistema operativo de Windows compatible con Skype empresarial Server.
    
- [Preparar Active Directory para Skype empresarial Server](prepare-active-directory.md) : Skype empresarial Server funciona estrechamente con Active Directory. Debe preparar el dominio de Active Directory para que funcione con Skype empresarial Server. Puede hacerlo mediante el Asistente para la implementación y solo se realiza una vez para el dominio. Esto se debe a que el proceso crea grupos y modifica el dominio, y solo debe hacerlo una vez.
    
- [Crear registros DNS para Skype empresarial Server](create-dns-records.md) : para que Skype empresarial Server funcione correctamente, es necesario que haya una serie de opciones de configuración de DNS en su ubicación. Esto es para que los clientes sepan cómo tener acceso a los servicios y los servidores que se conocen entre sí. Esta configuración solo debe realizarse una vez por cada implementación, ya que una vez asignada una entrada DNS, estará disponible en todo el dominio.
    
- [Cree y publique una nueva topología en Skype empresarial Server](create-and-publish-new-topology.md) : antes de poder instalar el sistema de Skype empresarial Server en cada uno de los servidores de la topología, debe crear una topología y publicarla. Al publicar una topología, se carga la información de topología en la base de datos del almacén de administración central. Si se trata de un grupo de servidores Enterprise Edition, se crea la base de datos del almacén de administración central la primera vez que se publica una nueva topología. Si esta es la edición estándar, debe ejecutar el proceso preparar el primer servidor Standard Edition del Asistente para la implementación antes de publicar una topología. Esto se prepara para Standard Edition mediante la instalación de una instancia de SQL Server Express Edition y la creación del almacén de administración central.
    
- [Instalar Skype empresarial Server en los servidores de la topología](install-skype-for-business-server.md) : una vez que se carga la topología en el almacén de administración central y Active Directory sabe qué servidores realizarán cada rol, debe instalar el sistema de Skype empresarial Server en cada uno de los servidores de la topología.
    
- [Compruebe la topología en Skype empresarial Server](verify-the-topology.md) : una vez que haya publicado la topología y los componentes del sistema de Skype empresarial Server instalados en cada uno de los servidores de la topología, estará preparado para comprobar que la topología funciona como se esperaba. Esto incluye la comprobación de que la configuración se ha propagado a todos los servidores de Active Directory para que todo el dominio sepa que Skype empresarial está disponible en el dominio.
    

