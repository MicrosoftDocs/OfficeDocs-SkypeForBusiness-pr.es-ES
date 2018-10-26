---
title: 'Lync Server 2013: Implementar tipos de dirección IP en un servidor perimetral'
TOCTitle: Implementar tipos de dirección IP en un servidor perimetral
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48275590
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar tipos de dirección IP en un servidor perimetral para Lync Server 2013

 

_**Última modificación del tema:** 2012-06-14_

Usando Generador de topologías, realice los pasos del siguiente procedimiento para implementar tipos de direcciones IP en un Servidor perimetral.

## Para implementar tipos de direcciones IP en un servidor perimetral

1.  En el Generador de topologías, en **Grupos de servidores perimetrales** , haga clic con el botón secundario en el servidor dentro de un grupo y seleccione **Editar propiedades** (otra opción es seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción** ).

2.  En la ventana **Editar propiedades** , seleccione la configuración de dirección IP que quiera admitir. En las siguientes figuras se muestra una configuración de pila dual para la interfaz interna y la interfaz externa.
    
    **Interfaz interna del servidor perimetral**
    
    ![Página de propiedades generales de Lync Server](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Página de propiedades generales de Lync Server")
    
    **Interfaz de servidor perimetral externo interfaz de pila dual**
    
    ![Página de configuración del próximo salto/externa de Lync Server](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Página de configuración del próximo salto/externa de Lync Server")

3.  Debe proporcionar las direcciones internas y externas apropiadas para cada tipo de dirección que seleccione.

