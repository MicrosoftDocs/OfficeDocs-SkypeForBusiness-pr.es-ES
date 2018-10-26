---
title: 'Lync Server 2013: Establecer conectividad de mensajería instantánea pública'
TOCTitle: Establecer conectividad de mensajería instantánea pública
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48275843
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Establecer conectividad de mensajería instantánea pública en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-08_

Si su organización desea admitir la conectividad de mensajería instantánea pública con AOL, no puede usar al Asistente para la implementación de Lync Server para solicitar el certificado. En su lugar, realice los pasos del siguiente procedimiento.

## Configurar conectividad de mensajería instantánea pública

1.  En un servidor front-end, abra el Generador de topologías. Expanda los Grupos de servidores perimetrales y, a continuación, haga clic con el botón secundario en Servidor perimetral o Grupo de servidores perimetrales. Seleccione Editar propiedades.

2.  En Editar propiedades en General, seleccione Habilitar federación para este grupo de servidores perimetrales (Puerto 5061). Haga clic en Aceptar.

3.  Haga clic en Acción, seleccione Topología y, finalmente, Publicar. Cuando se le solicite en Publicar la topología, seleccione Siguiente. Una vez completado el proceso de publicación, haga clic en Finalizar.

4.  En el servidor perimetral, abra el asistente para la implementación de Lync Server. Haga clic en Instalar o en Actualizar Lync Server System y, a continuación, en Instalar o desinstalar componentes de Lync Server. Haga clic en Ejecutar nuevamente.

5.  En Instalar componentes de Lync Server, haga clic en Siguiente. La pantalla de resumen mostrará las acciones a medida que se ejecuten. Una vez finalizada la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en Finalizar para completar la implementación.

## Para crear una solicitud de certificado para la interfaz externa del servidor perimetral para que admita la conectividad de mensajería instantánea pública con AOL

1.  Cuando la plantilla requerida está disponible para la entidad emisora de certificados, utilice el siguiente cmdlet de Windows PowerShell de en el servidor perimetral para solicitar el certificado
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    El nombre de certificado predeterminado de la plantilla usada para Lync Server es Web Server. Solo especifique el \<nombre de plantilla\> si tiene que usar una plantilla que sea diferente de la plantilla predeterminada.
    
    > [!IMPORTANT]  
    > Si su organización desea admitir la conectividad de mensajería instantánea pública con AOL, debe utilizar Windows PowerShell en lugar del Asistente para certificados para solicitar el certificado que se asignará a la arista externa para el servicio perimetral de acceso. Esto es porque la plantilla de la entidad emisora de certificados (CA) de servidor Web que utiliza el Asistente para certificados para solicitar un certificado no es compatible con la configuración del cliente de EKU. Antes de utilizar Windows PowerShell para crear el certificado, el Administrador de entidad emisora de certificados debe crear e implementar una nueva plantilla que sea compatible con cliente EKU.
    

