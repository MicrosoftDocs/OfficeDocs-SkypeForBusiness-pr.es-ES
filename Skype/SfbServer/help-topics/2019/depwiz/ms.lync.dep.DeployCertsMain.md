---
title: Asistente para certificados
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
description: Para solicitar, asignar, quitar o ver certificados, use el Asistente para certificados. Debe haber iniciado sesión como miembro del grupo RTCUniversalServerAdmins. No hace falta pertenecer a ningún otro grupo para solicitar un certificado a una entidad de certificación pública. Para solicitar un certificado de infraestructura de clave pública (PKI) de su organización, es necesario que confirme lo que adicionales, si hay alguno, pertenencias a grupos que necesitará. Durante la tarea de la solicitud, puede escribir las credenciales que se utilizará para solicitar que el certificado desde su PKI entidad emisora de certificados.
ms.openlocfilehash: d700a6cae510bbc12ed2e37c9c3df166d2704269
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="certificate-wizard"></a><span data-ttu-id="6cec0-107">Asistente para certificados</span><span class="sxs-lookup"><span data-stu-id="6cec0-107">Certificate Wizard</span></span>
 
<span data-ttu-id="6cec0-108">El Asistente para certificados se usa para **solicitar**, **asignar**, **quitar** o **ver** certificados.</span><span class="sxs-lookup"><span data-stu-id="6cec0-108">To **Request**, **Assign**, **Remove**, or **View** certificates, you use the Certificate Wizard.</span></span> <span data-ttu-id="6cec0-109">Debe haber iniciado sesión como miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6cec0-109">You must be logged in as a member of the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="6cec0-110">No hace falta pertenecer a ningún otro grupo para solicitar un certificado a una entidad de certificación pública.</span><span class="sxs-lookup"><span data-stu-id="6cec0-110">To request a certificate from a public certification authority (CA), you do not need any additional group memberships.</span></span> <span data-ttu-id="6cec0-111">Para solicitar un certificado de infraestructura de clave pública (PKI) de su organización, es necesario que confirme lo que adicionales, si hay alguno, pertenencias a grupos que necesitará.</span><span class="sxs-lookup"><span data-stu-id="6cec0-111">To request a certificate from your organization's public key infrastructure (PKI), you need to confirm what additional—if any—group memberships you will need.</span></span> <span data-ttu-id="6cec0-112">Durante la tarea de la solicitud, puede escribir las credenciales que se utilizará para solicitar que el certificado desde su PKI entidad emisora de certificados.</span><span class="sxs-lookup"><span data-stu-id="6cec0-112">During the Request task, you can enter alternate credentials that will be used to request the certificate from your PKI's issuing CA.</span></span>
  
<span data-ttu-id="6cec0-113">Para solicitar un nuevo certificado, haga clic en **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="6cec0-113">To request a new certificate, click **Request**.</span></span>
  
<span data-ttu-id="6cec0-114">Para asignar un certificado que todavía no se haya asignado, haga clic en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="6cec0-114">To assign a certificate that has not been assigned yet, click **Assign**.</span></span>
  
<span data-ttu-id="6cec0-115">Para quitar un certificado que ya se había asignado, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="6cec0-115">To remove a certificate that you have previously assigned, click **Remove**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6cec0-p103">El botón **Quitar** solo está disponible si ya se había asignado un certificado. Si el botón **Quitar** no está disponible (atenuado), significa que no hay ningún certificado asignado.</span><span class="sxs-lookup"><span data-stu-id="6cec0-p103">The **Remove** button will be available only if a certificate has been previously assigned. If the **Remove** button is unavailable (dimmed), there is no certificate assigned.</span></span>
  
<span data-ttu-id="6cec0-118">Para ver un certificado asignado, haga clic en **Ver**.</span><span class="sxs-lookup"><span data-stu-id="6cec0-118">To view an assigned certificate, click **View**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6cec0-p104">El botón **Ver** solo estará disponible si ya se había asignado un certificado. Si el botón **Ver** está atenuado en gris, significa que no hay ningún certificado asignado.</span><span class="sxs-lookup"><span data-stu-id="6cec0-p104">The **View** button will be available only if a certificate has been previously assigned. If the **View** button is greyed out, there is no certificate assigned.</span></span>
  
<span data-ttu-id="6cec0-121">Para actualizar la pantalla de asignación de certificados, haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="6cec0-121">To refresh the current certificate assignment screen, click **Refresh**.</span></span>
  
<span data-ttu-id="6cec0-122">Para importar un certificado que no figure en el almacén de certificados, haga clic en **Importar certificado**.</span><span class="sxs-lookup"><span data-stu-id="6cec0-122">To import a certificate that is not present in the certificate store, click **Import Certificate**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6cec0-123">La opción **Importar certificado** suele usarse para procesar un certificado que se recibe a través de un proceso distinto al de una solicitud del Asistente para certificados.</span><span class="sxs-lookup"><span data-stu-id="6cec0-123">**Import Certificate** is typically used to process a certificate that is received through a process other than a request from the Certificate Wizard.</span></span> <span data-ttu-id="6cec0-124">Por ejemplo, el administrador de la PKI crea un certificado y hace que esté disponible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="6cec0-124">For example, your PKI administrator creates a certificate and makes it available to you.</span></span> <span data-ttu-id="6cec0-125">**Importar certificado** de uso para importar el certificado en el certificado del equipo almacenar y ponerlo a disposición de Skype para Business Server asignar.</span><span class="sxs-lookup"><span data-stu-id="6cec0-125">Use **Import Certificate** to import the certificate into the computer's certificate store and make it available to Skype for Business Server to assign.</span></span>
  
<span data-ttu-id="6cec0-p106">Para completar el proceso de pedir una solicitud de certificado a una entidad de certificación de la organización que precisa la aprobación de un administrador de la entidad de certificación, haga clic en **Procesar solicitud pendiente**. La solicitud de certificado aparecerá con el estado de pendiente y mostrará el número de identificación de la solicitud pendiente. Para seguir procesando un certificado que tenga el estado de pendiente, haga clic en **Actualizar** para habilitar el botón **Procesar solicitud pendiente**. El botón **Procesar solicitud pendiente** dejará de estar deshabilitado (atenuado). A continuación, puede intentar recuperar la solicitud pendiente; sin embargo, la solicitud continuará teniendo el estado de pendiente hasta que se emita el certificado o el administrador de la entidad de certificación lo deniegue. El botón no estará disponible si no quedan solicitudes pendientes válidas creadas por el Asistente para certificados.</span><span class="sxs-lookup"><span data-stu-id="6cec0-p106">To complete the process of requesting a certificate request from a CA in your organization that requires CA administrator approval, click **Process Pending Request**. The certificate request will have returned a status of pending, and also displays the identification number of the pending request. To continue processing a certificate with a pending status, click **Refresh** to enable the **Process Pending Request** button. The **Process Pending Request** button will no longer be unavailable (dimmed). You can then attempt to retrieve the pending request, but the status of the request will remain pending until the certificate is issued or denied by the CA administrator. The button will be unavailable if there are no valid pending requests that have been created by the Certificate Wizard.</span></span>
  

