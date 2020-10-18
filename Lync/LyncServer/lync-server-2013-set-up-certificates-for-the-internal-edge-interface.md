---
title: 'Lync Server 2013: configurar certificados para la interfaz perimetral interna'
description: 'Lync Server 2013: configurar certificados para la interfaz perimetral interna.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52473069735d4f48c247367194139c479e71293f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575406"
---
# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a>Configurar certificados para la interfaz perimetral interna en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

<div>


> [!IMPORTANT]  
> Al ejecutar el Asistente para certificados, asegúrese de que ha iniciado sesión usando una cuenta que es miembro de un grupo con los permisos asignados adecuados para el tipo de plantilla de certificado que use. De forma predeterminada, una solicitud de certificado 2013 de Lync Server usará la plantilla de certificado del servidor Web. Si usa una cuenta que es miembro del grupo RTCUniversalServerAdmins para solicitar un certificado usando esta plantilla, compruebe que el grupo tenga asignados los permisos Inscribir necesarios para usar la plantilla.



</div>

En la interfaz interna de cada servidor perimetral se necesita un único certificado. Estos certificados pueden ser emitidos por una entidad de certificación (CA) de empresa interna o por una CA pública. Si su organización tiene una CA interna implementada, puede ahorrarse el gasto que supone usar certificados públicos mediante el uso de la CA interna para emitir el certificado para la interfaz interna. Puede usar una CA interna de Windows Server 2008 o una CA de Windows Server 2008 R2 para crear estos certificados.

Para obtener más información sobre este y otros requisitos de certificado, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Para definir certificados en la interfaz perimetral interna en un sitio, siga los procedimientos descritos en esta sección para hacer lo siguiente:

1.  Descargue la cadena de certificación de CA para la interfaz interna en cada servidor perimetral.

2.  Importe la cadena de certificación de CA para la interfaz interna en cada servidor perimetral.

3.  Cree la solicitud de certificado para la interfaz interna en un servidor perimetral, denominado primer servidor perimetral.

4.  Importe el certificado para la interfaz interna en el primer servidor perimetral.

5.  Importe el certificado en los demás servidores perimetrales de este sitio (o en los servidores implementados detrás del equilibrador de carga).

6.  Asigne el certificado para la interfaz interna de cada servidor perimetral.

Si tiene más de un sitio con servidores perimetrales (es decir, una topología perimetral de varios sitios) o distintos conjuntos de servidores perimetrales implementados detrás de diferentes equilibradores de carga, debe seguir estos pasos en cada sitio que tenga servidores perimetrales y en cada conjunto de servidores perimetrales implementados detrás de un equilibrador de carga diferente.

<div>


> [!NOTE]  
> Los pasos de los procedimientos descritos en esta sección se basan en el uso de una CA de Windows Server &nbsp; 2008, Windows server &nbsp; 2008 &nbsp; R2 CA, Windows Server 2012 CA o Windows Server 2012 R2 CA para crear un certificado para cada servidor perimetral. Para obtener instrucciones detalladas sobre cómo usar cualquier otra CA, vea la documentación relacionada. De forma predeterminada, todos los usuarios autenticados tienen los derechos de usuario adecuados para solicitar certificados.<BR>Los procedimientos descritos en esta sección se basan en la creación de solicitudes de certificado en el servidor perimetral como parte del proceso de implementación de servidores perimetrales. Es posible crear solicitudes de certificado mediante el servidor front-end. Puede usarlo para completar la solicitud de certificado antes de lo previsto en el proceso de planeación e implementación, antes de iniciar la implementación de los servidores perimetrales. Para ello, asegúrese de que el certificado que solicite pueda exportarse con una clave privada.<BR>En los procedimientos descritos en esta sección se usa un archivo .cer y un archivo .p7b para el certificado. Si usa un tipo de archivo distinto, modifique los procedimientos de la forma pertinente.



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a>Para descargar la cadena de certificación de CA de la interfaz interna mediante el sitio web certsrv

1.  Inicie sesión en un servidor de Lync Server 2013 en la red interna (es decir, no en el servidor perimetral) como miembro del grupo de **administradores** .

2.  Ejecute el comando siguiente en el símbolo del sistema; para ello, haga clic en **Inicio**, en **Ejecutar** y escriba:
    
        https://<name of your Issuing CA Server>/certsrv
    
    Por ejemplo:
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > Si usa una CA de empresa de Windows Server 2008 o Windows Server 2008 R2, debe usar https, en lugar de http.

    
    </div>

3.  En la página web certsrv de la CA que emite el certificado, en **Seleccione una tarea**, haga clic en **Descargar certificado de CA, cadena de certificados o CRL**.

4.  En **Descargar certificado de CA, cadena de certificados o CRL**, haga clic en **Descargar cadena de certificados de CA**.

5.  En el cuadro de diálogo **Descarga de archivos**, haga clic en **Guardar**.

6.  Guarde el archivo .p7b en el disco duro del servidor y, a continuación, cópielo en una carpeta en cada servidor perimetral.
    
    <div>
    

    > [!NOTE]  
    > El archivo .p7b contiene todos los certificados que figuran en la ruta de certificación. Para ver la ruta de certificación, abra el certificado de servidor y haga clic en la ruta de certificación.

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a>Para exportar la cadena de certificación de CA de la interfaz interna mediante MMC

1.  Puede exportar el certificado raíz de la entidad de certificación desde cualquier equipo unido a un dominio mediante Microsoft Management Console (MMC). Haga clic en **Inicio**, elija **Ejecutar** y escriba **MMC**.

2.  En la consola MMC, haga clic en **Archivo** y en **Agregar o quitar**.

3.  En la lista del cuadro de diálogo **Agregar o quitar complemento**, seleccione **Certificados** y luego haga clic en **Agregar**. Cuando se le indique, seleccione **Cuenta de equipo**. En el cuadro de diálogo **Seleccionar equipo**, seleccione **Equipo local**. Haga clic en **Finalizar**. Haga clic en **Aceptar**.

4.  Expanda **Certificados (equipo local)**. Expanda **Entidades de certificación raíz de confianza**, seleccione **Certificados**.

5.  Haga clic en el certificado raíz emitido por su CA. Haga clic con el botón secundario en el certificado, seleccione **Todas las tareas**, seleccione **Exportar**. Se abrirá el **Asistente para exportación de certificados**.

6.  En el **Asistente para exportación de certificados**, haga clic en **Siguiente**.

7.  En el cuadro de diálogo **Formato de archivo de exportación**, seleccione un formato para exportar. Se recomienda el **estándar de sintaxis de mensajes criptográficos: \# certificados PKCS 7 (. P7B)**. Si selecciona el **estándar de sintaxis de mensajes criptográficos: \# certificados PKCS 7 (. P7B)**, seleccione la casilla **incluir todos los certificados en la ruta de certificación si es posible** para exportar la cadena de certificados, incluido el certificado de CA raíz y los certificados de CA intermedios. Haga clic en **Siguiente**.

8.  En el cuadro de diálogo **Archivo que se va a exportar** de la entrada de nombre de archivo, escriba una ruta y nombre de archivo para el certificado exportado (la extensión predeterminada es .p7b). De manera opcional, haga clic en **Examinar**, localice un directorio en el que colocar el certificado exportado y especifique un nombre para el certificado exportado. Haga clic en **Guardar**. Haga clic en **Siguiente**.

9.  Repase el resumen de acciones y haga clic en **Finalizar** para completar la exportación del certificado. Haga clic en **Aceptar** para confirmar si la exportación se ha completado correctamente.

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a>Para importar la cadena de certificación de CA para la interfaz interna

1.  En cada servidor perimetral, abra Microsoft Management Console (MMC). Para ello, haga clic en **Inicio**, en **Ejecutar**, escriba **mmc** en el cuadro **Abrir** y, a continuación, haga clic en **Aceptar**.

2.  En el menú **Archivo**, haga clic en **Agregar o quitar complemento** y, a continuación, en **Agregar**.

3.  En el cuadro **Agregar complementos independientes**, haga clic en **Certificados** y, a continuación, en **Agregar**.

4.  En el cuadro de diálogo **Complemento de certificados**, haga clic en **Cuenta de equipo** y, a continuación, haga clic en **Siguiente**.

5.  En el cuadro de diálogo **Seleccionar equipo**, asegúrese de que la casilla **Equipo local: (el equipo en el que se está ejecutando esta consola)** esté activada y, a continuación, haga clic en **Finalizar**.

6.  Haga clic en **Cerrar** y, a continuación, en **Aceptar**.

7.  En el árbol de la consola, expanda **Certificados (equipo local)**, haga clic con el botón secundario en **Entidades de certificación raíz de confianza**, elija **Todas las tareas** y, a continuación, haga clic en **Importar**.

8.  En el asistente, en **Archivo para importar**, especifique el nombre de archivo del certificado (es decir, el nombre del archivo que especificó al descargar la cadena de certificación de CA para la interfaz interna en el procedimiento anterior).

9.  Repita este procedimiento en todos los servidores perimetrales.

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a>Para crear la solicitud de certificado para la interfaz interna

1.  En uno de los servidores perimetrales, inicie el Asistente para la implementación y junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**.
    
    <div>
    

    > [!NOTE]  
    > Si tiene varios servidores perimetrales en una ubicación de un grupo de servidores, puede ejecutar el Asistente para certificados en cualquiera de los servidores perimetrales.<BR>Después de ejecutar el Paso 3 por primera vez, el botón pasará a mostrar <STRONG>Ejecutar de nuevo</STRONG> y no se mostrará una marca de verificación verde que indica la correcta finalización de la tarea hasta que todos los certificados requeridos se hayan solicitado, instalado y asignado.

    
    </div>

2.  En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.

3.  En la página **Solicitud de certificado **, haga clic en **Siguiente **.

4.  En la página **Solicitudes retrasadas o inmediatas**, haga clic en **Prepare ahora la solicitud, pero envíela más tarde**.

5.  En la página **archivo de solicitud de certificado** , escriba la ruta de acceso completa y el nombre de archivo en el que se va a guardar la solicitud (por ejemplo, **c: \\ CERT \_ Internal \_ Edge. cer**).

6.  En la página **Especificar plantilla de certificado alternativa**, para usar una plantilla distinta a la plantilla predeterminada WebServer, active la casilla **Usar plantilla de certificado alternativa para la entidad de certificación seleccionada**.

7.  En la página **Nombre y configuración de seguridad**, siga este procedimiento:
    
      - En **Nombre descriptivo**, escriba un nombre para mostrar para el certificado (por ejemplo, perímetro interno).
    
      - En **Longitud de bits**, especifique la longitud de bits (normalmente, el valor predeterminado es **2048**).
        
        <div>
        

        > [!NOTE]  
        > Las longitudes de bits mayores son más seguras, pero afectan de forma negativa a la velocidad.

        
        </div>
    
      - Si el certificado debe poder exportarse, active la casilla **Marcar la clave privada del certificado como exportable**.

8.  En la página **Información de la organización**, escriba un nombre para la organización y la unidad organizativa (por ejemplo, una división o departamento).

9.  En la página **Información geográfica**, escriba la información de ubicación.

10. En la página **Nombre de sujeto/nombres alternativos de sujeto**, la información se rellenará automáticamente gracias al asistente que se muestra.

11. En la página **Configurar nombres alternativos de sujeto**, especifique cualquier nombre alternativo de sujeto adicional que necesite.

12. En la página **Resumen de la solicitud**, revise la información del certificado que se va a usar para generar la solicitud.

13. Una vez completados los comandos, haga lo siguiente:
    
      - Para visualizar el registro de la solicitud de certificación, haga clic en **Ver registro**.
    
      - Para completar la solicitud de certificación, haga clic en **Siguiente**.

14. En la página **Archivo de solicitud de certificados**, haga lo siguiente:
    
      - Para visualizar el archivo de solicitud de firma de certificado (CSR) que se ha generado, haga clic en **Ver**.
    
      - Para cerrar el asistente, haga clic en **Finalizar**.

15. Envíe este archivo a su CA (por correo electrónico u otro método compatible con la organización para su CA de empresa) y, cuando reciba el archivo de respuesta, copie el nuevo certificado en este equipo de modo que esté disponible para importarlo.

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a>Para importar el certificado para la interfaz interna

1.  Inicie sesión en el servidor perimetral donde haya creado la solicitud de certificado como miembro del grupo de administradores locales.

2.  En el Asistente para la implementación, junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.
    
    Después de ejecutar el Paso 3 por primera vez, el botón pasará a mostrar **Ejecutar de nuevo**, pero no se mostrará una marca de verificación verde que indica la correcta finalización de la tarea hasta que todos los certificados requeridos se hayan solicitado, instalado y asignado.

3.  En la página **Tareas de certificado disponibles**, haga clic en **Importar un certificado de un archivo .P7b, .pfx o .cer**.

4.  En la página **Importar certificado**, escriba la ruta de acceso completa y el nombre de archivo del certificado que haya solicitado y recibido para la interfaz interna de este servidor perimetral (o haga clic en **Examinar** para buscar y seleccionar el archivo).

5.  Si va a importar certificados para otros miembros del grupo de servidores que contengan una clave privada, active la casilla **El archivo del certificado contiene clave privada de certificado** y especifique la contraseña.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>Para exportar el certificado con la clave privada para servidores perimetrales de un grupo

1.  Inicie sesión como miembro del grupo Administradores en el mismo servidor perimetral en el que desea importar el certificado.

2.  Haga clic en **Inicio**, en **Ejecutar** y escriba **MMC**.

3.  Desde la consola MMC, haga clic en **Archivo**, haga clic en **Agregar o quitar complemento**.

4.  En la página Agregar o quitar complemento, haga clic en **Certificados** y en **Agregar**.

5.  En el cuadro de diálogo del complemento certificados, seleccione **Cuenta de equipo**. Haga clic en **Siguiente**. En Seleccionar equipo, marque **Equipo local (el equipo en el que se está ejecutando esta consola)**. Haga clic en **Finalizar**. Haga clic en **Aceptar** para completar la configuración de la consola MMC.

6.  Haga doble clic en **Certificados (equipo local)** para ampliar los almacenes de certificados. Haga doble clic en **Personal** y doble clic de nuevo en **Certificados**.
    
    <div>
    

    > [!IMPORTANT]  
    > Si no hay certificados en el almacén Certificados Personal para el equipo local, no habrá una clave privada asociada al certificado que se importó. Revise los pasos para la solicitud y la importación. Si el problema continúa, póngase en contacto con su administrador o proveedor de entidades de certificación.

    
    </div>

7.  En el almacén Certificados Personal del equipo local, haga clic con el botón secundario en el certificado que va a exportar. Haga clic en **Todas las tareas** y en **Exportar**.

8.  En el asistente para exportación de certificados, haga clic en **Siguiente**. Seleccione **Exportar la clave privada** y haga clic en **Siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Si la opción <STRONG>Exportar la clave privada</STRONG> no se encuentra disponible, se deberá a que no se marcó la clave privada asociada a este certificado para la exportación. Tendrá que solicitar de nuevo el certificado y, antes de que se inicie la exportación, deberá asegurarse de que el certificado está marcado para que se exporte la clave privada. Póngase en contacto con el administrador o proveedor de entidades de certificación.

    
    </div>

9.  En el cuadro de diálogo formatos de archivo de exportación, seleccione **intercambio de información personal: PKCS \# 12 (. PFX)** y, a continuación, seleccione lo siguiente:
    
      - Si es posible, incluir todos los certificados en la ruta de acceso de certificación
    
      - Exportar todas las propiedades extendidas
        
        <div>
        

        > [!WARNING]  
        > Cuando exporte el certificado desde un servidor perimetral, no seleccione <STRONG>Eliminar la clave privada si la exportación es correcta</STRONG>. Al seleccionar esta opción es necesario importar el certificado y la clave privada a este servidor perimetral.

        
        </div>
    
    Haga clic en **Siguiente ** para continuar.

10. Si desea asignar una contraseña para proteger la clave privada, escriba dicha contraseña. Vuelva a escribir la contraseña para confirmarla. Haga clic en **Siguiente**.

11. Escriba la ruta y nombre de archivo del certificado exportado, utilizando la extensión de archivo .pfx. La ruta debe estar accesible para todos los demás servidores perimetrales del grupo o disponible para el transporte mediante medios extraíbles, por ejemplo, una unidad flash USB. Haga clic en **Siguiente**.

12. Revise el resumen del cuadro de diálogo del asistente para exportación de certificados y haga clic en **Finalizar**.

13. Haga clic en **Aceptar** cuando el cuadro de diálogo informe de que la exportación ha concluido correctamente

14. Importe el archivo de certificado exportado a los demás servidores perimetrales siguiendo los pasos descritos en los procedimientos de [configuración de certificados para la interfaz perimetral externa para Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a>Para asignar el certificado interno en los servidores perimetrales

1.  En cada servidor perimetral, en el Asistente para la implementación, junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.

2.  En la página **Tareas de certificado disponibles**, haga clic en **Asignar un certificado existente**.

3.  En la página **Asignación del certificado**, seleccione **Interfaz perimetral interna** en la lista.

4.  En la página **Almacén de certificados**, seleccione el certificado que importó para el perímetro interno (en el procedimiento anterior).

5.  En la página **Resumen de asignación de certificados**, revise su configuración y, a continuación, haga clic en **Siguiente** para asignar los certificados.

6.  En la página de finalización del asistente, haga clic en **Finalizar**.

7.  Después de asignar el certificado de perímetro interno, abra el complemento Certificado en cada servidor, expanda **Certificados (equipo local)**, expanda **Personal**, haga clic en **Certificados** y, a continuación, compruebe que aparezca el certificado de perímetro interno en el panel de detalles.

8.  Si la implementación incluye varios servidores perimetrales, repita este procedimiento con todos los servidores perimetrales.

</div>

</div>

<span> </span>

</div>

</div>

</div>

