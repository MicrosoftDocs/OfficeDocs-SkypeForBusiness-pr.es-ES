---
title: 'Lync Server 2013: uso de la herramienta de personalización de Office (OCT)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2203c4169075b7b906156bf3436e61011f873a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a><span data-ttu-id="49f8a-102">Uso de la herramienta de personalización de Office (OCT) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49f8a-102">Using the Office Customization Tool (OCT) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49f8a-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="49f8a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="49f8a-104">La herramienta de personalización de Office (OCT) forma parte del programa de instalación y es la herramienta recomendada para muchas personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="49f8a-104">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="49f8a-105">Mediante el uso de la OCT, se personaliza Office y se guardan las personalizaciones en un archivo. MSP de personalización del programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="49f8a-105">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="49f8a-106">El archivo se coloca en la carpeta Actualizaciones del punto de instalación en red.</span><span class="sxs-lookup"><span data-stu-id="49f8a-106">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="49f8a-107">Al instalar Office, el programa de instalación busca un archivo de personalización del programa de instalación en la carpeta actualizaciones y aplica las personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="49f8a-107">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="49f8a-108">La carpeta updates solo se puede usar para implementar actualizaciones de software durante una instalación inicial de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="49f8a-108">The Updates folder can be used only to deploy software updates during an initial installation of Office 2013.</span></span>

<span data-ttu-id="49f8a-109">La OCT forma parte de la instalación y está incluida en las versiones de licencia por volumen del producto.</span><span class="sxs-lookup"><span data-stu-id="49f8a-109">The OCT is part of setup and it is included in volume license versions of the product.</span></span> <span data-ttu-id="49f8a-110">Para ejecutar la OCT, escriba `setup.exe /admin` en la línea de comandos desde la raíz del punto de instalación de red que contiene los archivos de origen de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="49f8a-110">You run the OCT by typing `setup.exe /admin` at the command line from the root of the network installation point that contains the Office 2013 source files.</span></span> <span data-ttu-id="49f8a-111">Por ejemplo, utilice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="49f8a-111">For example, use the following:</span></span>

`\\server\share\Office15\setup.exe /admin`

<span data-ttu-id="49f8a-112">Los administradores pueden utilizar la OCT para crear un archivo .msp de personalización de la instalación.</span><span class="sxs-lookup"><span data-stu-id="49f8a-112">Administrators use the OCT to create a setup customization .msp file.</span></span> <span data-ttu-id="49f8a-113">Como en Microsoft Office 2010 OCT, los administradores pueden personalizar las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="49f8a-113">As in the Microsoft Office 2010 OCT, administrators can customize the following areas:</span></span>

  - <span data-ttu-id="49f8a-114">**Configuración** de Se usa para especificar la ubicación de instalación predeterminada en el cliente y el nombre predeterminado de la organización, orígenes de instalación en red adicionales, clave de producto, contrato de licencia para el usuario final, nivel de presentación, versiones anteriores de Office que se van a quitar, programas personalizados que se ejecutarán durante la instalación, configuración de seguridad y propiedades de configuración.</span><span class="sxs-lookup"><span data-stu-id="49f8a-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>

  - <span data-ttu-id="49f8a-115">**Características** Se usa para configurar las opciones de usuario y personalizar el modo en que se instalan las características de Office.</span><span class="sxs-lookup"><span data-stu-id="49f8a-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="49f8a-116">Los administradores pueden utilizar la OCT para especificar los valores iniciales predeterminados de la aplicación de Office para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="49f8a-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="49f8a-117">Los usuarios pueden modificar la mayoría de las opciones después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="49f8a-117">Users can modify most of the settings after the installation.</span></span>

  - <span data-ttu-id="49f8a-118">**Contenido adicional** Se usa para agregar o quitar archivos, para agregar o quitar entradas del registro y para configurar accesos directos.</span><span class="sxs-lookup"><span data-stu-id="49f8a-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>

  - <span data-ttu-id="49f8a-119">**Outlook** Se usa para personalizar el perfil de Outlook predeterminado de un usuario, especificar la configuración de Exchange, agregar cuentas, quitar cuentas y exportar\\configuraciones, y especificar los grupos de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="49f8a-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\\Receive groups.</span></span>

<span data-ttu-id="49f8a-120">Para obtener información sobre la OCT, <http://go.microsoft.com/fwlink/p/?linkid=267516>consulte.</span><span class="sxs-lookup"><span data-stu-id="49f8a-120">For information about the OCT, see <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

