# Tarea-5
# =====================================================================
# FASE 5 - EVALUACIÓN FINAL POA
# PROBLEMA 2: GESTIÓN DE PRECIOS DE MENÚ DE RESTAURANTE
# =====================================================================

def calcular_precio_final(producto, categoria_objetivo, umbral_precio):
    """
    Módulo para calcular el precio final de un producto 
    aplicando las reglas de negocio de la promoción.
    """
    nombre = producto[0]
    categoria = producto[1]
    precio_base = producto[2]
    
    # Lógica de Negocio: 15% de descuento si cumple categoría y supera el umbral
    if categoria.lower() == categoria_objetivo.lower() and precio_base > umbral_precio:
        descuento = precio_base * 0.15
        precio_final = precio_base - descuento
    else:
        precio_final = precio_base
        
    return precio_final


def main():
    # 1. MATRIZ: Creación de la matriz con 6 productos [Nombre, Categoría, Precio Base]
    menu_restaurante = [
        ["Hamburguesa Angus", "Comida Rapida", 25000],
        ["Papas Fritas", "Acompanamientos", 8000],
        ["Pizza Familiar", "Comida Rapida", 45000],
        ["Jugo Natural", "Bebidas", 7000],
        ["Lasana de Pollo", "Platos Fuertes", 28000],
        ["Cerveza Artesanal", "Bebidas", 12000]
    ]
    
    # Definición de variables para la promoción (Categoría objetivo y Umbral)
    categoria_promo = "Comida Rapida"
    umbral_promo = 15000
    
    print("=" * 60)
    print(f"   PROMOCIÓN: 15% OFF en '{categoria_promo}' (Precios > ${umbral_promo})")
    print("=" * 60)
    
    # 2. SALIDA: Mostrar cada producto con su precio base y final
    # Formato de la cabecera
    print(f"{'Producto':<22} | {'Categoría':<16} | {'P. Base':<9} | {'P. Final':<9}")
    print("-" * 60)
    
    for producto in menu_restaurante:
        # Llamado al módulo de cálculo
        precio_final_prod = calcular_precio_final(producto, categoria_promo, umbral_promo)
        
        # Impresión formateada de los resultados
        print(f"{producto[0]:<22} | {producto[1]:<16} | ${producto[2]:<8} | ${precio_final_prod:<8.0f}")
        
    print("=" * 60)

# Ejecución del programa principal
if __name__ == "__main__":
    main()
