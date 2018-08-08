---
title: Implemente servidores perimetrales en Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Resumen: Obtenga información sobre cómo implementar servidores perimetrales en su Skype para el entorno de servidor empresarial.'
ms.openlocfilehash: fc4791918ef078bc43e73f8e404aad758531eb21
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003127"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Implemente servidores perimetrales en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo implementar servidores perimetrales en su Skype para el entorno de servidor empresarial.
  
Las secciones siguientes contienen los pasos que deben seguirse después de que se ha revisado la Skype para la documentación de [planeación para las implementaciones de servidor perimetral de Skype para Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) un servidor de negocio. Los pasos de implementación son los siguientes:
  
- Interfaces de red
    
- Instalación
    
- Certificados
    
- Iniciar los servidores perimetrales
    
## <a name="network-interfaces"></a>Interfaces de red

Como se indicó en planeación, va ya sea a configurar la interfaz de red con DNS en la red perimetral que hospeda los servidores perimetrales, o sin DNS en la red perimetral.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Configuración de la interfaz con servidores DNS en la red perimetral

1. Instale a dos adaptadores de red para cada servidor perimetral, uno para la interfaz interna y otro para la interfaz externa.
    
    > [!NOTE]
    > Las subredes internas y externas no deben ser enrutables entre sí. 
  
2. En la interfaz externa, configurará **una** de las siguientes opciones:
    
   a. Tres direcciones IP estáticas en la subred de la red perimetral externa y apunte la puerta de enlace predeterminada a la interfaz interna del firewall externo. Configure el adaptador DNS para apuntar a un par de servidores DNS perimetrales.
    
   b. Una dirección IP estática en la subred de la red perimetral externa y apunte la puerta de enlace predeterminada a la interfaz interna del firewall externo. Configure el adaptador DNS para apuntar a un par de servidores DNS perimetrales. Esta configuración sólo es aceptable si ha configurado la topología para tienen valores no estándar en las asignaciones de puerto, que se describe en el artículo de [crear la topología perimetral de Skype para Business Server](create-your-edge-topology.md) anteriormente.
    
3. En la interfaz interna, configure una dirección IP estática en la subred de red de perímetro interno y no establece una puerta de enlace predeterminada. Configure el adaptador DNS para apuntar al menos a un servidor DNS, preferiblemente a un par de servidores DNS perimetrales.
    
4. Cree rutas estáticas persistentes en la interfaz interna para todas las redes internas donde residen los clientes, Skype para Business Server y los servidores de mensajería unificada de Exchange (UM).
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Configuración de la interfaz sin servidores DNS en la red perimetral

1. Instale a dos adaptadores de red para cada servidor perimetral, uno para la interfaz interna y otro para la interfaz externa.
    
    > [!NOTE]
    > Las subredes internas y externas no deben ser enrutables entre sí. 
  
2. En la interfaz externa, configurará **una** de las siguientes opciones:
    
   a. Tres direcciones IP estáticas en la subred de la red perimetral externa. También necesitará configurar la puerta de enlace predeterminada en la interfaz externa, por ejemplo, define el enrutador a través de internet o el firewall externo como puerta de enlace predeterminada. Configure el adaptador DNS para apuntar a un servidor DNS externo, a poder ser, a un par de servidores DNS externos.
    
   b. Una dirección IP estática en la subred de la red perimetral externa. También necesitará configurar la puerta de enlace predeterminada en la interfaz externa, por ejemplo, define el enrutador a través de internet o el firewall externo como puerta de enlace predeterminada. Configure el adaptador DNS para apuntar a un servidor DNS externo o, a poder ser, a un par de servidores DNS externos. Esta configuración sólo es aceptable si ha configurado la topología para tienen valores no estándar en las asignaciones de puerto, que se describe en el artículo de [crear la topología perimetral de Skype para Business Server](create-your-edge-topology.md) anteriormente.
    
3. En la interfaz interna, configure una dirección IP estática en la subred de red de perímetro interno y no establece una puerta de enlace predeterminada. Deje también la configuración del adaptador DNS vacía.
    
4. Cree rutas estáticas persistentes en la interfaz interna para todas las redes internas donde residen los clientes, Skype para Business Server y los servidores de mensajería unificada de Exchange (UM).
    
5. Edite el archivo HOST en cada servidor perimetral para contener un registro para el servidor del próximo salto o IP virtual (VIP). Este registro será el Director, servidor Standard Edition o grupo de servidores Front-End configurado como la dirección del servidor perimetral próximo salto en el generador de topología. Si usa equilibrio de carga DNS, incluya una línea para cada miembro de servidores del próximo salto.
    
## <a name="installation"></a>Instalación

Para completar estos pasos correctamente, debe haber seguido los pasos descritos en el artículo de [crear la topología perimetral de Skype para Business Server](create-your-edge-topology.md) .
  
1. Inicie sesión en el servidor que ha sido configurar para la función de servidor perimetral con una cuenta que se encuentra en el grupo de administradores locales.
    
2. Necesitará el archivo de configuración de la topología que copia al final de la documentación de la topología de servidores perimetrales en este equipo. Obtenga acceso a los medios externos en los que ha colocado ese archivo de configuración (como una unidad USB o compartir).
    
3. Iniciar el **Asistente para la implementación**.
    
4. Una vez que se abre el asistente, haga clic en **instalar o actualización de Skype para Business Server System**.
    
5. El asistente ejecutará comprobaciones para ver si ya está instalado nada. Ya que esta es la primera vez que se ejecuta al asistente, desea iniciar en **paso 1. Instalar almacén de configuración Local.**
    
6. Aparecerá el cuadro de diálogo **almacén de configuración Local réplica de Administración Central** . Debe hacer clic en **Importar desde un archivo (recomendado para los servidores perimetrales)**.
    
7. Desde aquí, vaya a la ubicación de la topología que exportó anteriormente, seleccione el archivo .zip, haga clic en **Abrir** y después haga clic en **Siguiente**.
    
8. El Asistente para la implementación va a leer el archivo de configuración y escribir el archivo de configuración XML en el equipo local.
    
9. Cuando el proceso **Ejecución de comandos** se complete, haga clic en **Finalizar**.
    
10. En el Asistente para la implementación, haga clic en **paso 2. Instalar o quitar Skype para los componentes de servidor empresariales**. El Asistente para, a continuación, instalará el Skype para los componentes de servidor perimetral de negocio especificado en el archivo de configuración XML que se ha almacenado en el equipo local.
    
11. Una vez que la instalación s completa, puede mover en los pasos descritos en la sección de **certificados** más adelante.
    
## <a name="certificates"></a>Certificados

Los requisitos de certificado para el servidor perimetral pueden encontrarse en la documentación de planeación de certificado de borde. Los pasos para configurar los certificados se muestran a continuación.
  
> [!NOTE]
> Al ejecutar al Asistente para certificados, debe haber iniciado sesión como una cuenta con los permisos correctos para el tipo de plantilla de certificado que se va a usar. De forma predeterminada, un Skype para la solicitud de certificado de servidor empresarial se va a usar la plantilla de certificado de servidor Web. Si ha iniciado sesión con una cuenta que sea miembro del grupo RTCUniversalServerAdmins para solicitar un certificado a través de esta plantilla, compruebe que el grupo se han asignado los permisos de inscripción para usar esa plantilla. 
  
### <a name="internal-edge-interface-certificates"></a>Certificados de interfaz de servidor perimetral interno

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. descargar o exportar la cadena de certificación de CA

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp;un. Descargar con el sitio web certsrv

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;. Inicie sesión en un Skype para Business Server en la red interna como un miembro del grupo de administradores locales.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Abra copia de seguridad **Iniciar**y **ejecute** (o **Buscar** y **Ejecutar** ) y, a continuación, escriba lo siguiente:
    
  ```
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Por ejemplo:
    
  ```
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. En la página web de la entidad emisora certsrv, en **Seleccione una tarea**, haga clic en **Descargar certificado de CA, cadena de certificados o CRL**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. En **Descargar certificado de CA, cadena de certificados o CRL**, haga clic en **Descargar cadena de certificados de CA**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. En el cuadro **Descarga de archivos**, haga clic en **Guardar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VI. Guarde el archivo. p7b en la unidad de disco duro en el servidor y, a continuación, cópielo en una carpeta en cada uno de los servidores perimetrales.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. Exportar con MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;. Puede exportar el certificado raíz de la CA de cualquier equipo unido al dominio con MMC. Vaya a **Inicio** y **Ejecutar** o abra **Búsqueda** y escriba **MMC** para abrir.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. En la consola MMC, haga clic en **Archivo** y después haga clic en **Agregar o quitar complemento**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. En la lista **Agregar o quitar complementos** del cuadro de diálogo elija **Certificados** y luego haga clic en **Agregar**. Cuando aparezca el aviso, seleccione **Cuenta de equipo** y después **Siguiente**. En el diálogo **Seleccionar equipo**, seleccione **Equipo local**. Haga clic en **Finalizar** y después en **Aceptar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Expanda **certificados (equipo Local)**. Expanda **entidades de certificación raíz de confianza**. Seleccione **certificados**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Haga clic en el certificado raíz emitido por su CA. Haga clic con el botón derecho en el certificado, seleccione **Todas las tareas** en el menú y después seleccione **Exportar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VI. El **Asistente para exportación de certificados** se abre. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VII. En el diálogo **Formato de archivo de exportación**, elija el formato que desee para exportar. Le recomendamos **Estándar de sintaxis de cifrado de mensajes: certificados PKCS #7 (P7b)**. Si eso es así como su elección, recuerde también seleccione la casilla de verificación **incluir todos los certificados en la ruta de certificación si es posible** , tal y como se va a exportar también la cadena de certificados, incluido el certificado de entidad emisora de certificados raíz y todos los certificados intermedios. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VIII. En el diálogo **Archivo que se va a exportar**, en la entrada de nombre de archivo, escriba una ruta de acceso y un nombre de archivo (la extensión predeterminada será .p7b) para el certificado exportado. Si es más fácil para usted, elija el botón **Examinar** para ir a la ubicación que desea guardar el certificado exportado a y nombre aquí el certificado exportado. Haga clic en **Guardar**y, a continuación, en **siguiente** cuando esté listo.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IX. Repase el resumen de acciones y haga clic en **Finalizar** para completar la exportación del certificado. Haga clic en **Aceptar** para confirmar si la exportación se ha completado correctamente.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x. Copie el archivo. p7b en cada uno de los servidores perimetrales.
    
### <a name="2-import-the-ca-certification-chain"></a>2. importar la cadena de certificación de CA

&nbsp;&nbsp;&nbsp;un. En cada servidor perimetral, abra MMC (elija **Iniciar** y **Ejecutar**o **búsqueda**y escriba **MMC** para abrir).
    
&nbsp;&nbsp;&nbsp;b. En el menú **Archivo**, haga clic en **Agregar o quitar complemento** y después en **Agregar**.
    
&nbsp;&nbsp;&nbsp;c. En el cuadro **Agregar o quitar complementos**, haga clic en **Certificados** y luego en **Agregar**.
    
&nbsp;&nbsp;&nbsp;d.. En el cuadro de diálogo **Complemento de certificados**, haga clic en **Cuenta de equipo** y luego haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;e. En el cuadro de diálogo **Seleccionar equipo**, asegúrese de que la casilla **Equipo local: (el equipo en el que se está ejecutando esta consola)** esté activada y luego haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;f. Haga clic en **Cerrar** y después en **Aceptar**.
    
&nbsp;&nbsp;&nbsp;g. En el árbol de la consola, expanda **Certificados (equipo local)**, haga clic con el botón derecho en **Entidades de certificación raíz de confianza**, vaya a **Todas las tareas** y después haga clic en **Importar**.
    
&nbsp;&nbsp;&nbsp;h. En el asistente que aparece, en el cuadro de texto **Archivo para importar**, especifique el nombre de archivo del certificado (el nombre que le ha asignado al archivo .p7b en la sección anterior). Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;. El botón de radio **Colocar todos los certificados en el siguiente almacén, como entidades de certificación raíz de confianza** debería estar seleccionado. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;j. Revise el resumen y haga clic en **Finalizar** para completar la importación.
    
&nbsp;&nbsp;&nbsp;k. Esto deberá realizarse para cada servidor perimetral que se va a implementar.
    
### <a name="3-create-the-certificate-request"></a>3. crear la solicitud de certificado

&nbsp;&nbsp;&nbsp;un. Inicie sesión en uno de los servidores perimetrales, inicie el Asistente para la implementación y en **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar** (o **Ejecutar de nuevo**, si ya ha ejecutado este asistente).
    
&nbsp;&nbsp;&nbsp;b. En la página **Solicitud de certificado**, asegúrese de que **Certificado de servidor perimetral interno** está seleccionado y haga clic en **Solicitud**.
    
&nbsp;&nbsp;&nbsp;c. En la página **solicitudes retrasadas o inmediatas** , elija **enviar la solicitud inmediatamente a una entidad de certificación en línea** si tiene acceso a uno desde su entorno perimetral o en **Preparar la petición ahora, pero enviarla más tarde** en caso contrario.
    
&nbsp;&nbsp;&nbsp;d.. En la página **Archivo de solicitud de certificado**, escriba la ruta completa y el nombre de archivo de dónde se ha guardado el archivo (como c:\SkypeInternalEdgeCert.cer). Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;e. En la página **Especificar plantilla de certificado alternativa**, para usar una plantilla distinta a la plantilla predeterminada WebServer, active la casilla **Usar plantilla de certificado alternativa para la entidad de certificación seleccionada**. En caso contrario, no haga nada.
    
&nbsp;&nbsp;&nbsp;f. En la página   Nombre y configuración de seguridad, siga este procedimiento:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;. En **Nombre descriptivo**, escriba un nombre para mostrar para el certificado (por ejemplo, servidor perimetral interno).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. En **Longitud de bits**, elija su longitud de bits (el valor predeterminado es 2048, puede ser mayor y ser más segura, pero hará ralentizar el rendimiento).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Si necesita un certificado exportable, debe activar la casilla **Marcar la clave privada del certificado como exportable**.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;g. En la página **Información de la organización**, escriba el nombre para la organización y la unidad organizativa (OU). Puede introducir la división o departamento (TI, por ejemplo).
    
&nbsp;&nbsp;&nbsp;h. En la página **Información geográfica**, escriba la información de ubicación.
    
&nbsp;&nbsp;&nbsp;. En la página **Nombre de sujeto/Nombres alternativos de sujeto**, el asistente debe rellenarla automáticamente.
    
&nbsp;&nbsp;&nbsp;j. En la página **Configurar nombres alternativos de sujeto adicionales**, tiene que agregar los nombres alternativos de sujeto adicionales que necesita.
    
&nbsp;&nbsp;&nbsp;k. En la página **Resumen de la solicitud** , busque a través de la información del certificado que se va a usar para generar la solicitud. Si necesita realizar cambios, vuelva atrás y hágalos ahora.
    
&nbsp;&nbsp;&nbsp;l. A continuación, haga clic en **siguiente** para generar el archivo CSR que necesitará para proporcionar a la entidad de certificación (también puede hacer clic en **Ver registro** para buscar en el registro de la solicitud de certificado).
    
&nbsp;&nbsp;&nbsp;m. Una vez que se ha generado la solicitud, puede hacer clic en **Ver** para ver el certificado y **Finalizar** para cerrar la ventana. Tiene que darle el contenido del archivo CSR a su CA, para que puedan generar un certificado para importar a este equipo en la siguiente sección.
    

### <a name="4-import-the-certificate"></a>4. importar el certificado

&nbsp;&nbsp;&nbsp;un. Inicie sesión, como un miembro del grupo Administradores local, para el servidor perimetral realizados desde la solicitud de certificado en el último procedimiento.
    
&nbsp;&nbsp;&nbsp;b. En el Asistente para la implementación, junto a **paso 3. Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.
    
&nbsp;&nbsp;&nbsp;c. En la página **Tareas de certificado disponibles**, haga clic en **Importar un certificado de un archivo .P7b, .pfx o .cer**.
    
&nbsp;&nbsp;&nbsp;d.. En la página **Importar certificado**, escriba la ruta de acceso completa y el nombre de archivo del certificado que obtuvo en la sección anterior (o puede hacer clic en **Examinar** para buscar y seleccionar el archivo de esta forma).
    
&nbsp;&nbsp;&nbsp;e. Si va a importar certificados para otros miembros del grupo de servidores perimetrales y su certificado contiene una clave privada, asegúrese de seleccionar la casilla de verificación del **archivo de certificado que contiene la clave privada del certificado** y especificar la contraseña. Haga clic en **Siguiente** para continuar.
    
&nbsp;&nbsp;&nbsp;f. En la página**Resumen** , haga clic en **siguiente** una vez que haya confirmado la información y **Finalizar** una vez que el certificado se ha importado correctamente.
    
 
### <a name="5-export-the-certificate"></a>5. exportar el certificado

&nbsp;&nbsp;&nbsp;un. Asegúrese de que ha iniciado sesión en el servidor perimetral que desea importar el certificado a anteriormente, como un miembro del grupo de administradores locales.
    
&nbsp;&nbsp;&nbsp;b. Haga clic en **Inicio**, **en ejecutar** (o abrir **búsqueda** ), y escriba **MMC**.
    
&nbsp;&nbsp;&nbsp;c. Desde la consola MMC, haga clic en **Archivo** y haga clic en **Agregar o quitar complemento**.
    
&nbsp;&nbsp;&nbsp;d.. Desde el cuadro **Agregar o quitar complementos**, haga clic en **Certificados** y en **Agregar**.
    
&nbsp;&nbsp;&nbsp;e. En el cuadro de diálogo **Complementos de certificados**, elija **Cuenta de equipo**. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;f. En el diálogo **Seleccionar equipo** seleccione **Equipo local: (el equipo en el que se está ejecutando esta consola)**. Haga clic en **Finalizar**. Haga clic en **Aceptar** y la configuración de la consola MMC se ha completado.
    
&nbsp;&nbsp;&nbsp;g. Haga doble clic en **Certificados (equipo local)** para expandir los almacenes de certificados. Haga doble clic en **Personal** y después haga clic en **Certificados**.
    
  > [!NOTE]
  > Es posible que aquí, y no puede ver todos los certificados en los certificados personales almacenar para el equipo local. No es necesario para extensiones alrededor, si la clave no existe, s importado certificado no tiene una clave privada asociada con él. Intente la solicitud de importación pasos anteriores una vez más y si está seguro de que tiene todo lo que derecho, hable con el Administrador de la entidad emisora de certificados o el proveedor. 
  
&nbsp;&nbsp;&nbsp;h. En el **almacén de certificados personales** del equipo local, haga clic en el certificado que va a exportar. Seleccione **Todas las tareas** desde el menú resultante y luego haga clic en **Exportar**.
    
&nbsp;&nbsp;&nbsp;. En el **Asistente para exportación de certificados**, haga clic en **siguiente**. Seleccione **Sí, exportar la clave privada**. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;j. En el cuadro de diálogo **Formatos de archivo de exportación**, seleccione **Intercambio de información personal: PKCS#12 (.PFX)** y luego seleccione lo siguiente:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;. Si es posible, incluir todos los certificados en la ruta de acceso de certificación.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Exportar todas las propiedades extendidas.
    
   > [!NOTE]
   > **NUNCA** seleccione **Eliminar la clave privada si la exportación es correcta**. Aquí significa que se debe volver a importar el certificado y la clave privada, volver a este servidor perimetral.
  
&nbsp;&nbsp;&nbsp;k. Si desea asignar una contraseña para proteger la clave privada, puede escribir una contraseña para la clave privada. Vuelva a escribir la contraseña para confirmarla y después haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;l. Escriba la ruta y el nombre de archivo del certificado exportado, con la extensión de archivo **.pfx**. La ruta de acceso ya sea necesario que esté accesible a los demás servidores perimetrales en el grupo de servidores o que necesitará para mover el archivo por medio de medios externos (por ejemplo, una unidad USB). Haga clic en **siguiente** cuando haya hecho su elección.
    
&nbsp;&nbsp;&nbsp;m. Revise el resumen del cuadro de diálogo del **asistente para exportación de certificados** y haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;n. Haga clic en **Aceptar** en el cuadro de diálogo de exportación correcta.
    
 
### <a name="6-assign-the-certificate"></a>6. asignar el certificado

&nbsp;&nbsp;&nbsp;un. En cada servidor perimetral, en el Asistente para la implementación, junto a **paso 3. Solicitar, instalar o asignar certificados**, haga clic en **volver a ejecutar**.
    
&nbsp;&nbsp;&nbsp;b. En la página **Tareas de certificado disponibles**, haga clic en **Asignar un certificado existente**.
    
&nbsp;&nbsp;&nbsp;c. En la página **Asignación del certificado**, seleccione **Interfaz perimetral interna** en la lista.
    
&nbsp;&nbsp;&nbsp;d.. En la página **Almacén de certificados** , seleccione el certificado que ha importado para el perímetro interno (desde la sección anterior).
    
&nbsp;&nbsp;&nbsp;e. En la página **Resumen de asignación de certificados**, vea la configuración y después haga clic en **Siguiente** para asignar el certificado.
    
&nbsp;&nbsp;&nbsp;f. En la página de finalización del asistente, haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;g. Una vez que haya completado este procedimiento, es una realmente buena idea para abrir el complemento MMC de certificados en cada servidor perimetral, expanda **certificados (equipo Local)**, expanda **Personal**, haga clic en **certificados**y confirme que el perímetro interno el certificado aparece en el panel de detalles.
    
### <a name="external-edge-interface-certificates"></a>Certificados de interfaz de servidor perimetral externo

 
### <a name="1-create-the-certificate-request"></a>1. crear la solicitud de certificado

&nbsp;&nbsp;&nbsp;un. Inicie sesión en uno de los servidores perimetrales, inicie el Asistente para la implementación y en **paso 3: solicitar, instalar o asignar certificados, haga clic en ejecutar** (o **Ejecutar de nuevo**, si ya ha ejecutado este asistente).
    
&nbsp;&nbsp;&nbsp;b. En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.
    
&nbsp;&nbsp;&nbsp;c. En la página **Solicitud de certificado**, asegúrese de que **Certificado de servidor perimetral externo** está seleccionado y haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;d.. En la página **Solicitudes retrasadas o inmediatas**, haga clic en **Prepare ahora la solicitud, pero envíela más tarde**.
    
&nbsp;&nbsp;&nbsp;e. En la página **Archivo de solicitud de certificado**, escriba la ruta completa y el nombre de archivo de dónde se ha guardado el archivo (como c:\SkypeInternalEdgeCert.cer). Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;f. En la página **Especificar plantilla de certificado alternativa**, para usar una plantilla distinta a la plantilla predeterminada WebServer, active la casilla **Usar plantilla de certificado alternativa para la entidad de certificación seleccionada**.
    
&nbsp;&nbsp;&nbsp;g. En la página   Nombre y configuración de seguridad, siga este procedimiento:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;. En **Nombre descriptivo**, escriba un nombre para mostrar para el certificado (por ejemplo, servidor perimetral externo).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. En **Longitud de bits**, elija su longitud de bits (el valor predeterminado es 2048, puede ser mayor y ser más segura, pero hará ralentizar el rendimiento).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Si necesita un certificado exportable, debe activar la casilla **Marcar la clave privada del certificado como exportable**.
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;h. En la página **Información de la organización**, escriba el nombre para la organización y la unidad organizativa (OU). Puede introducir la división o departamento (TI, por ejemplo).
    
&nbsp;&nbsp;&nbsp;. En la página **Información geográfica**, escriba la información de ubicación.
    
&nbsp;&nbsp;&nbsp;j. En la página **Nombre de sujeto/Nombres alternativos de sujeto**, el asistente debe rellenar la información necesaria automáticamente.
    
&nbsp;&nbsp;&nbsp;k. En la página **Configuración del dominio SIP en nombres alternativos de sujeto (SAN)** , active la casilla de verificación de dominio para agregar un sip.<sipdomain> entrada a la lista de nombres alternativos del sujeto.
    
&nbsp;&nbsp;&nbsp;l. En la página **Configurar nombres alternativos de sujeto adicionales**, tiene que agregar los nombres alternativos de sujeto adicionales que necesita.
    
&nbsp;&nbsp;&nbsp;m. En la página **Resumen de la solicitud** , busque a través de la información del certificado que se va a usar para generar la solicitud. Si necesita realizar cambios, vuelva atrás y hágalos ahora.
    
&nbsp;&nbsp;&nbsp;n. Cuando esté listo, haga clic en **siguiente** para generar el archivo CSR que necesitará para proporcionar a la entidad de certificación (también puede hacer clic en **Ver registro** para buscar en el registro de la solicitud de certificado).
    
&nbsp;&nbsp;&nbsp;o. Una vez que se ha generado la solicitud, puede hacer clic en **Ver** para ver el certificado y **Finalizar** para cerrar la ventana. Tiene que darle el contenido del archivo CSR a su CA, para que puedan generar un certificado para importar a este equipo en la siguiente sección.
    
&nbsp;&nbsp;&nbsp;p. (OPCIONAL) Puede que, al presentar el contenido de la CSR, se le pida cierta información, tal como se muestra a continuación (las CA varían en gran medida, por lo que puede que esto no sea necesario):
    
  - **Microsoft** como la plataforma de servidor
    
  - **IIS** como la versión
    
  - **Web Server** como el tipo de uso
    
  - **PKCS7** como el formato de respuesta
    
 
### <a name="2-import-the-certificate"></a>2. importar el certificado

&nbsp;&nbsp;&nbsp;un. Inicie sesión, como un miembro del grupo Administradores local, para el servidor perimetral realizados desde la solicitud de certificado en el último procedimiento.
    
&nbsp;&nbsp;&nbsp;b. En el Asistente para la implementación, junto a **paso 3. Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.
    
&nbsp;&nbsp;&nbsp;c. En la página **Tareas de certificado disponibles**, haga clic en **Importar un certificado de un archivo .P7b, .pfx o .cer**.
    
&nbsp;&nbsp;&nbsp;d.. En la página **Importar certificado**, escriba la ruta de acceso completa y el nombre de archivo del certificado que obtuvo en la sección anterior (o puede hacer clic en **Examinar** para buscar y seleccionar el archivo de esta forma). Si el certificado contiene una clave privada, asegúrese de seleccionar el **archivo de certificado contiene la clave privada del certificado**y escriba la contraseña de la clave privada. Haga clic en **Siguiente** cuando esté listo.
    
&nbsp;&nbsp;&nbsp;e. En la página **Importar resumen de certificado**, revise el resumen y luego haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;f. En la página **Ejecución de comandos** , puede revisar el resultado de la importación cuando se haya completado, haga clic en **Ver registro**. Haga clic en **Finalizar** para completar la importación del certificado.
    
&nbsp;&nbsp;&nbsp;g. Si tiene otros servidores perimetrales en un grupo de servidores, debe seguir los próximos dos procedimientos. Si se trata de un servidor perimetral independiente, haya terminado con los certificados externos.
    
 
### <a name="3-export-the-certificate"></a>3. exportar el certificado

&nbsp;&nbsp;&nbsp;un. Asegúrese de que ha iniciado sesión en el servidor perimetral que desea importar el certificado para como administrador local.
    
&nbsp;&nbsp;&nbsp;b. Haga clic en **Inicio**, **en ejecutar** (o abrir **búsqueda** ), y escriba **MMC**.
    
&nbsp;&nbsp;&nbsp;c. Desde la consola MMC, haga clic en **Archivo** y luego haga clic en **Agregar o quitar complemento**.
    
&nbsp;&nbsp;&nbsp;d.. Desde el cuadro **Agregar o quitar complementos**, haga clic en **Certificados** y en **Agregar**.
    
&nbsp;&nbsp;&nbsp;e. En el cuadro de diálogo **Complementos de certificados**, elija **Cuenta de equipo**. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;f. En el diálogo **Seleccionar equipo** seleccione **Equipo local: (el equipo en el que se está ejecutando esta consola)**. Haga clic en **Finalizar**. Haga clic en **Aceptar** y la configuración de la consola MMC se ha completado.
    
&nbsp;&nbsp;&nbsp;g. Haga doble clic en **Certificados (equipo local)** para expandir los almacenes de certificados. **Haga doble clic en Personal** y después haga clic en **Certificados**.
    
   > [!NOTE]
   > Es posible que aquí, y no puede ver todos los certificados en los certificados personales almacenar para el equipo local. No es necesario para extensiones alrededor, si la clave no existe, s importado certificado no tiene una clave privada asociada con él. Intente la solicitud de importación pasos anteriores una vez más y si está seguro de que tiene todo lo que derecho, hable con el Administrador de la entidad emisora de certificados o el proveedor. 
  
&nbsp;&nbsp;&nbsp;h. En el **almacén de certificados personales** del equipo local, haga clic en el certificado que va a exportar. **Seleccione Todas las tareas** desde el menú resultante y luego haga clic en **Exportar**.
    
&nbsp;&nbsp;&nbsp;. En el **Asistente para exportación de certificados**, haga clic en **siguiente**. Seleccione **Sí, exportar la clave privada**. Haga clic en **Siguiente**.
    
   > [!NOTE]
   > Si no está disponible **en Sí, exportar la clave privada** , la clave privada para este certificado no está marcada para la exportación antes de que ha captado. Tiene que volver a solicitar el certificado del proveedor, con la clave privada establecida en exportar, antes de realizar esto correctamente.
  
&nbsp;&nbsp;&nbsp;j. En el cuadro de diálogo Formatos de archivo de exportación, seleccione Intercambio de información personal: PKCS#12 (.PFX) y luego seleccione lo siguiente:
    
 &nbsp;&nbsp;&nbsp;. Si es posible, incluir todos los certificados en la ruta de acceso de certificación.
    
 &nbsp;&nbsp;&nbsp;II. Exportar todas las propiedades extendidas.
    
   > [!NOTE]
   > **NUNCA** seleccione **Eliminar la clave privada si la exportación es correcta**. Aquí significa que se debe volver a importar el certificado y la clave privada, volver a este servidor perimetral.
  
&nbsp;&nbsp;&nbsp;k. Si desea asignar una contraseña para proteger la clave privada, puede escribir una contraseña para la clave privada. Vuelva a escribir la contraseña para confirmarla y después haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;l. Escriba la ruta y el nombre de archivo del certificado exportado, con la extensión de archivo **.pfx**. La ruta de acceso ya sea necesario que esté accesible a los demás servidores perimetrales en el grupo de servidores o que necesitará para mover el archivo por medio de medios externos (por ejemplo, una unidad USB). Haga clic en **siguiente** cuando haya hecho su elección.
    
&nbsp;&nbsp;&nbsp;m. Revise el resumen del cuadro de diálogo del **asistente para exportación de certificados** y haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;n. Haga clic en **Aceptar** en el cuadro de diálogo de exportación correcta.
    
&nbsp;&nbsp;&nbsp;o. Ahora debe volver a la importación de la sección certificado antes de esto, importar el certificado a todos los servidores perimetrales restantes y, a continuación, continuar con la asignación, a continuación.
    
 
### <a name="4-assign-the-certificate"></a>4. asignar el certificado

&nbsp;&nbsp;&nbsp;un. En **cada** servidor de borde en el Asistente para la implementación, junto a **paso 3. Solicitar, instalar o asignar certificados**, haga clic en **volver a ejecutar**.
    
&nbsp;&nbsp;&nbsp;b. En la página **Tareas de certificado disponibles**, haga clic en **Asignar un certificado existente**.
    
&nbsp;&nbsp;&nbsp;c. En la página **Asignación de certificados** , seleccione **Servidor perimetral externo** en la lista.
    
&nbsp;&nbsp;&nbsp;d.. En la página **Almacén de certificados** , seleccione el certificado que ha importado para el perímetro externo (desde la sección anterior).
    
&nbsp;&nbsp;&nbsp;e. En la página **Resumen de asignación de certificados**, vea la configuración y después haga clic en **Siguiente** para asignar el certificado.
    
&nbsp;&nbsp;&nbsp;f. En la página de finalización del asistente, haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;g. Una vez que haya completado este procedimiento, es una realmente buena idea para abrir el complemento MMC de certificados en cada servidor, expanda **certificados (equipo Local)**, expanda **Personal**, haga clic en **certificados**y confirme que el perímetro interno el certificado aparece en el panel de detalles.
    
   > [!NOTE]
   > También tendrá que configurar los certificados para el servidor de proxy inverso. 
  
## <a name="starting-the-edge-servers"></a>Iniciar los servidores perimetrales

Una vez finalizada la instalación, debe iniciar los servicios en cada servidor perimetral en la implementación:
  
1. En cada servidor perimetral, en el **Asistente para la implementación**, junto a **paso 4: iniciar servicios**, haga clic en **Ejecutar**.
    
2. En la página de **Inicio de Skype para servicios de servidor empresarial** , revise la lista de servicios y, a continuación, haga clic en **siguiente** para iniciar los servicios.
    
3. Una vez iniciados los servicios, haga clic en **Finalizar** para cerrar el asistente.
    
4. (Opcional) Aún en el **Paso 4: Iniciar servicios**, haga clic en **Estado de los servicios**.
    
5.  En **MMC de servicios** en cada servidor, compruebe que todas las Skype para servicios de Business Server se están ejecutando.
    

