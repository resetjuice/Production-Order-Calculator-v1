<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora v4.2 - Reset Juice Style</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #2d6c3e 0%, #4a9b5e 100%);
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 15px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            overflow: hidden;
        }
        
        .header {
            background: linear-gradient(135deg, #2d6c3e, #4a9b5e);
            color: white;
            padding: 30px;
            text-align: center;
        }
        
        .header h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
            font-weight: 300;
        }
        
        .header p {
            font-size: 1.1em;
            opacity: 0.9;
        }
        
        .version-badge {
            background: rgba(255,255,255,0.2);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.9em;
            margin-top: 10px;
            display: inline-block;
        }
        
        .content {
            padding: 30px;
        }
        
        .product-insight {
            background: linear-gradient(135deg, #ff8c42, #ffa366);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 30px;
            border-left: 5px solid #e67735;
        }
        
        .product-insight h3 {
            color: white;
            margin-bottom: 15px;
        }

        .product-insight p {
            color: white;
        }
        
        .form-section {
            background: #f8f9fa;
            padding: 25px;
            border-radius: 10px;
            margin-bottom: 30px;
            border: 1px solid #e9ecef;
        }
        
        .form-section h3 {
            color: #2d6c3e;
            margin-bottom: 20px;
            font-size: 1.3em;
            border-bottom: 2px solid #4a9b5e;
            padding-bottom: 10px;
        }
        
        .input-group {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .input-field {
            display: flex;
            flex-direction: column;
        }
        
        .input-field label {
            font-weight: 600;
            color: #2d6c3e;
            margin-bottom: 5px;
            font-size: 0.9em;
        }
        
        .input-field input, .input-field select {
            padding: 12px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 1em;
            transition: border-color 0.3s ease;
        }
        
        .input-field input:focus, .input-field select:focus {
            outline: none;
            border-color: #4a9b5e;
            box-shadow: 0 0 0 3px rgba(74, 155, 94, 0.1);
        }
        
        .month-selector {
            margin-top: 10px;
            padding: 10px;
            background: #fff3cd;
            border: 1px solid #ffeaa7;
            border-radius: 5px;
            font-size: 0.85em;
        }
        
        .product-alert {
            padding: 15px;
            border-radius: 8px;
            margin-top: 15px;
            font-weight: 600;
        }
        
        .alert-danger {
            background: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }
        
        .alert-warning {
            background: #fff3cd;
            color: #856404;
            border: 1px solid #ffeaa7;
        }
        
        .alert-success {
            background: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }
        
        .alert-info {
            background: #d1ecf1;
            color: #0c5460;
            border: 1px solid #bee5eb;
        }
        
        .calculate-btn {
            background: linear-gradient(135deg, #2d6c3e, #4a9b5e);
            color: white;
            border: none;
            padding: 15px 40px;
            font-size: 1.1em;
            font-weight: 600;
            border-radius: 8px;
            cursor: pointer;
            transition: transform 0.2s ease;
            margin: 20px auto;
            display: block;
        }
        
        .calculate-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(45, 108, 62, 0.3);
        }
        
        .results {
            display: none;
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            padding: 30px;
            border-radius: 10px;
            margin-top: 30px;
            border: 2px solid #4a9b5e;
        }
        
        .results h3 {
            color: #2c3e50;
            margin-bottom: 25px;
            font-size: 1.5em;
            text-align: center;
        }
        
        .result-card {
            background: white;
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            border-left: 4px solid #4a9b5e;
        }
        
        .result-main {
            border-left-color: #4a9b5e;
            background: linear-gradient(135deg, #e8f5e8, #d4f1d4);
        }
        
        .result-card h4 {
            color: #2c3e50;
            margin-bottom: 10px;
            font-size: 1.1em;
        }
        
        .result-value {
            font-size: 1.8em;
            font-weight: bold;
            color: #2d6c3e;
        }
        
        .personalization-highlight {
            background: linear-gradient(135deg, #ff8c42, #ffa366);
            padding: 15px;
            border-radius: 8px;
            margin: 15px 0;
            color: white;
            font-weight: 600;
        }
        
        .calculation-details {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 8px;
            margin-top: 20px;
            border: 1px solid #dee2e6;
        }
        
        .calculation-step {
            margin-bottom: 15px;
            padding: 10px;
            background: white;
            border-radius: 5px;
            border-left: 3px solid #4a9b5e;
        }
        
        .normalization-highlight {
            background: linear-gradient(135deg, #4a9b5e, #2d6c3e);
            color: white;
            padding: 15px;
            border-radius: 8px;
            margin: 15px 0;
            font-weight: 600;
        }
        
        .comparison-table {
            background: white;
            padding: 20px;
            border-radius: 8px;
            margin: 20px 0;
            overflow-x: auto;
        }
        
        .comparison-table table {
            width: 100%;
            border-collapse: collapse;
        }
        
        .comparison-table th,
        .comparison-table td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid #dee2e6;
        }
        
        .comparison-table th {
            background: #4a9b5e;
            color: white;
            font-weight: 600;
        }
        
        .trend-analysis {
            margin-top: 20px;
            text-align: center;
        }
        
        .trend-indicator {
            display: inline-block;
            padding: 10px 20px;
            border-radius: 20px;
            font-weight: bold;
            margin: 10px;
        }
        
        .trend-up {
            background: #d4edda;
            color: #155724;
        }
        
        .trend-down {
            background: #f8d7da;
            color: #721c24;
        }
        
        .trend-stable {
            background: #fff3cd;
            color: #856404;
        }
        
        .methodology {
            background: #e8f4f8;
            padding: 20px;
            border-radius: 8px;
            margin-top: 30px;
            border: 1px solid #b8daff;
        }
        
        .methodology h4 {
            color: #004085;
            margin-bottom: 15px;
            font-size: 1.2em;
        }
        
        .methodology ul {
            color: #004085;
            margin-left: 20px;
        }
        
        .methodology li {
            margin-bottom: 8px;
        }
        
        .error {
            background: #f8d7da;
            color: #721c24;
            padding: 15px;
            border-radius: 8px;
            margin: 15px 0;
            border: 1px solid #f5c6cb;
        }

        .shelf-life-warning {
            background: #fff3cd;
            border: 2px solid #ffc107;
            padding: 15px;
            border-radius: 8px;
            margin: 15px 0;
            color: #856404;
            font-weight: 600;
        }

        .improvement-badge {
            background: linear-gradient(135deg, #4a9b5e, #6bb77b);
            color: white;
            padding: 8px 15px;
            border-radius: 20px;
            font-size: 0.85em;
            font-weight: 600;
            display: inline-block;
            margin: 5px;
        }

        .revolutionary-badge {
            background: linear-gradient(135deg, #ff8c42, #e67735);
            color: white;
            padding: 8px 15px;
            border-radius: 20px;
            font-size: 0.85em;
            font-weight: 600;
            display: inline-block;
            margin: 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Calculadora de Órdenes v4.2</h1>
            <p>Normalización Estacional - Máxima Precisión</p>
            <div class="version-badge">v4.2 - Normalización Estacional por Producto</div>
            <div style="margin-top: 10px;">
                <span class="revolutionary-badge">Normalización por Producto</span>
                <span class="improvement-badge">Promedio Ponderado</span>
                <span class="improvement-badge">Control Vida Útil</span>
                <span class="improvement-badge">Ajuste Stock</span>
            </div>
        </div>
        
        <div class="content">
            <div class="product-insight">
                <h3>Calculadora de Órdenes con Normalización Estacional</h3>
                <p>Sistema avanzado que elimina sesgos estacionales de datos históricos para generar predicciones de alta precisión, especialmente efectivo en cambios de temporada.</p>
            </div>
            
            <div class="form-section">
                <h3>🎯 Selección de Producto</h3>
                <div class="input-group">
                    <div class="input-field">
                        <label for="productSelect">Selecciona tu Producto</label>
                        <select id="productSelect" onchange="analyzeProduct()">
                            <option value="">-- Selecciona un producto --</option>
                            <optgroup label="🥕 Raíces y Vegetales">
                                <option value="carrot-rush-480">🥕 Carrot Rush 480ml (75 días)</option>
                                <option value="unbeetable-480">🔥 Unbeetable 480ml (80 días)</option>
                                <option value="unbeetable-350">🔥 Unbeetable 350ml (100 días)</option>
                            </optgroup>
                            <optgroup label="💚 Verdes">
                                <option value="skinny-green-480">💚 Skinny Green 480ml (75 días)</option>
                                <option value="skinny-green-350">💚 Skinny Green 350ml (100 días)</option>
                                <option value="greenergy-480">🌱 Greenergy 480ml (80 días)</option>
                                <option value="greenergy-350">🌱 Greenergy 350ml (100 días)</option>
                            </optgroup>
                            <optgroup label="🍍 Cítricos y Frutas">
                                <option value="pinebliss-480">🍍 Pinebliss 480ml (120 días)</option>
                                <option value="pinebliss-350">🍍 Pinebliss 350ml (120 días)</option>
                                <option value="spicy-limonata-480">🌶️ Spicy Limonata 480ml (120 días)</option>
                                <option value="c-master-480">🧡 C-Master 480ml (70 días)</option>
                                <option value="black-magic-480">⚫ Black Magic 480ml (135 días)</option>
                                <option value="tropik-glow-480">🌴 Tropik Glow 480ml (70 días)</option>
                            </optgroup>
                            <optgroup label="💪 Shots y Concentrados">
                                <option value="immune-boost-50">💪 Immune Boost 50ml (150 días)</option>
                                <option value="gingerlicious-50">🫚 Gingerlicious 50ml (150 días)</option>
                                <option value="gingerlicious-250">🫚 Gingerlicious 250ml (120 días)</option>
                            </optgroup>
                            <optgroup label="🥛 Leches Vegetales">
                                <option value="vitality-mylk-480">🥛 Vitality Mylk 480ml (20 días)</option>
                                <option value="coco-dream-480">🤍 Coco Dream 480ml (20 días)</option>
                                <option value="chokonut-480">🍫 Chokonut 480ml (25 días)</option>
                                <option value="coco-blast-480">🥥 Coco Blast 480ml (65 días)</option>
                            </optgroup>
                        </select>
                        <div id="productAlert"></div>
                    </div>
                    <div class="input-field">
                        <label for="targetMonth">Mes Objetivo</label>
                        <select id="targetMonth" onchange="updateSeasonalInfo()">
                            <option value="">Selecciona el mes</option>
                            <option value="enero">Enero</option>
                            <option value="febrero">Febrero</option>
                            <option value="marzo">Marzo</option>
                            <option value="abril">Abril</option>
                            <option value="mayo">Mayo</option>
                            <option value="junio">Junio</option>
                            <option value="julio">Julio</option>
                            <option value="agosto">Agosto</option>
                            <option value="septiembre">Septiembre</option>
                            <option value="octubre">Octubre</option>
                            <option value="noviembre">Noviembre</option>
                            <option value="diciembre">Diciembre</option>
                        </select>
                    </div>
                </div>
            </div>
            
            <div class="form-section">
                <h3>📈 Ventas de los Últimos 3 Meses (con Normalización Automática)</h3>
                <div class="input-group">
                    <div class="input-field">
                        <label for="month1">Mes 1 (más antiguo) - Peso: 20%</label>
                        <input type="number" id="month1" placeholder="Ej: 126" min="0">
                        <div class="month-selector">
                            <label for="month1Type">¿Qué mes fue?</label>
                            <select id="month1Type">
                                <option value="">Seleccionar mes...</option>
                                <option value="enero">Enero</option>
                                <option value="febrero">Febrero</option>
                                <option value="marzo">Marzo</option>
                                <option value="abril">Abril</option>
                                <option value="mayo">Mayo</option>
                                <option value="junio">Junio</option>
                                <option value="julio">Julio</option>
                                <option value="agosto">Agosto</option>
                                <option value="septiembre">Septiembre</option>
                                <option value="octubre">Octubre</option>
                                <option value="noviembre">Noviembre</option>
                                <option value="diciembre">Diciembre</option>
                            </select>
                        </div>
                    </div>
                    <div class="input-field">
                        <label for="month2">Mes 2 - Peso: 30%</label>
                        <input type="number" id="month2" placeholder="Ej: 80" min="0">
                        <div class="month-selector">
                            <label for="month2Type">¿Qué mes fue?</label>
                            <select id="month2Type">
                                <option value="">Seleccionar mes...</option>
                                <option value="enero">Enero</option>
                                <option value="febrero">Febrero</option>
                                <option value="marzo">Marzo</option>
                                <option value="abril">Abril</option>
                                <option value="mayo">Mayo</option>
                                <option value="junio">Junio</option>
                                <option value="julio">Julio</option>
                                <option value="agosto">Agosto</option>
                                <option value="septiembre">Septiembre</option>
                                <option value="octubre">Octubre</option>
                                <option value="noviembre">Noviembre</option>
                                <option value="diciembre">Diciembre</option>
                            </select>
                        </div>
                    </div>
                    <div class="input-field">
                        <label for="month3">Mes 3 (más reciente) - Peso: 50%</label>
                        <input type="number" id="month3" placeholder="Ej: 132" min="0">
                        <div class="month-selector">
                            <label for="month3Type">¿Qué mes fue?</label>
                            <select id="month3Type">
                                <option value="">Seleccionar mes...</option>
                                <option value="enero">Enero</option>
                                <option value="febrero">Febrero</option>
                                <option value="marzo">Marzo</option>
                                <option value="abril">Abril</option>
                                <option value="mayo">Mayo</option>
                                <option value="junio">Junio</option>
                                <option value="julio">Julio</option>
                                <option value="agosto">Agosto</option>
                                <option value="septiembre">Septiembre</option>
                                <option value="octubre">Octubre</option>
                                <option value="noviembre">Noviembre</option>
                                <option value="diciembre">Diciembre</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>

            <div class="form-section">
                <h3>📦 Inventario Actual</h3>
                <div class="input-group">
                    <div class="input-field">
                        <label for="currentStock">Stock Disponible Actual</label>
                        <input type="number" id="currentStock" placeholder="Ej: 45" min="0" value="0">
                        <small style="color: #666; margin-top: 5px;">Unidades que tienes actualmente en inventario</small>
                    </div>
                </div>
            </div>
            
            <button class="calculate-btn" onclick="calculateWithSeasonalNormalization()">Calcular con Normalización Estacional v4.2</button>
            
            <div id="results" class="results">
                <h3>Resultados con Normalización Estacional v4.2</h3>
                
                <div class="normalization-highlight" id="normalizationHighlight" style="display: none;">
                    <h5>Normalización Estacional Aplicada:</h5>
                    <div id="normalizationDetails">--</div>
                </div>
                
                <div class="result-card result-main">
                    <h4>🎯 CANTIDAD FINAL RECOMENDADA (NORMALIZADA)</h4>
                    <div class="result-value" id="recommendedOrder">--</div>
                    <p id="finalOrderDescription">Con normalización estacional + todas las mejoras v4.2</p>
                </div>
                
                <div class="comparison-table" id="comparisonTable" style="display: none;">
                    <h5>⚖️ Comparación: Sin Normalizar vs CON Normalización Estacional</h5>
                    <table>
                        <thead>
                            <tr>
                                <th>Método</th>
                                <th>Demanda Base</th>
                                <th>Demanda Estacional</th>
                                <th>Total + Seguridad</th>
                                <th>Diferencia vs Sin Normalizar</th>
                            </tr>
                        </thead>
                        <tbody id="comparisonTableBody">
                        </tbody>
                    </table>
                </div>
                
                <div id="shelfLifeWarning" class="shelf-life-warning" style="display: none;">
                    <strong>⚠️ Limitación por Vida Útil:</strong>
                    <div id="shelfLifeDetails">--</div>
                </div>
                
                <div class="result-card">
                    <h4>Demanda Base Normalizada</h4>
                    <div class="result-value" id="normalizedBaseDemand">--</div>
                    <p>Promedio ponderado después de normalización estacional</p>
                </div>
                
                <div class="result-card">
                    <h4>Demanda Estacional Final</h4>
                    <div class="result-value" id="seasonalDemand">--</div>
                    <p>Demanda base normalizada × factor estacional del mes objetivo</p>
                </div>
                
                <div class="result-card">
                    <h4>Factor Estacional del Mes Objetivo</h4>
                    <div class="result-value" id="seasonalFactor">--</div>
                    <p>Factor específico de este producto para el mes seleccionado</p>
                </div>
                
                <div class="result-card">
                    <h4>Stock de Seguridad Personalizado</h4>
                    <div class="result-value" id="safetyStock">--</div>
                    <p id="safetyStockDescription">Basado en demanda normalizada + volatilidad del producto</p>
                </div>

                <div class="result-card">
                    <h4>Ajuste por Stock Actual</h4>
                    <div class="result-value" id="stockAdjustment">--</div>
                    <p>Cantidad descontada por inventario disponible</p>
                </div>
                
                <div class="result-card">
                    <h4>Días de Cobertura Proyectada</h4>
                    <div class="result-value" id="coverageDays">--</div>
                    <p>Basado en demanda estacional normalizada</p>
                </div>
                
                <div class="trend-analysis">
                    <h4>Análisis de Tendencia (Normalizada)</h4>
                    <div id="trendIndicator">--</div>
                </div>
                
                <div class="calculation-details">
                    <h4>Cálculos de Normalización Paso a Paso</h4>
                    <div id="calculationSteps">--</div>
                </div>
            </div>
            
            <div class="methodology">
                <h4>Metodología v4.2: Normalización Estacional Revolucionaria</h4>
                <ul>
                    <li><strong>NUEVO: Normalización Estacional:</strong> Cada mes histórico se divide por su factor estacional específico del producto</li>
                    <li><strong>Eliminación de Sesgos:</strong> Los datos de temporada baja ya no contaminan predicciones de temporada alta</li>
                    <li><strong>Promedio Ponderado Normalizado:</strong> Se aplica después de la normalización para máxima precisión</li>
                    <li><strong>Control de Vida Útil Inteligente:</strong> Nunca recomienda más de lo vendible en días de caducidad</li>
                    <li><strong>Ajuste por Stock Actual:</strong> Descuenta automáticamente el inventario disponible</li>
                    <li><strong>Personalización por Producto:</strong> Cada jugo mantiene sus patrones estacionales únicos</li>
                    <li><strong>Comparaciones Transparentes:</strong> Muestra diferencia vs método sin normalizar</li>
                </ul>
            </div>
        </div>
    </div>

    <script>
        // Base de datos personalizada COMPLETA con todas las presentaciones
        const productDatabase = {
            'carrot-rush-480': {
                name: 'Carrot Rush 480ml',
                shelfLife: 75,
                seasonalIndices: {
                    'enero': 1.696, 'febrero': 1.304, 'marzo': 1.065, 'abril': 1.125,
                    'mayo': 1.147, 'junio': 1.119, 'julio': 1.082, 'agosto': 1.113,
                    'septiembre': 0.896, 'octubre': 0.725, 'noviembre': 0.548, 'diciembre': 0.180
                },
                volatilityMultiplier: 1.8,
                averageMonthly: 142
            },
            'immune-boost-50': {
                name: 'Immune Boost 50ml',
                shelfLife: 150,
                seasonalIndices: {
                    'enero': 1.093, 'febrero': 1.498, 'marzo': 0.804, 'abril': 1.315,
                    'mayo': 1.099, 'junio': 1.484, 'julio': 1.047, 'agosto': 1.008,
                    'septiembre': 0.839, 'octubre': 0.656, 'noviembre': 0.867, 'diciembre': 0.289
                },
                volatilityMultiplier: 1.8,
                averageMonthly: 476
            },
            'skinny-green-480': {
                name: 'Skinny Green 480ml',
                shelfLife: 75,
                seasonalIndices: {
                    'enero': 1.459, 'febrero': 1.149, 'marzo': 1.074, 'abril': 1.195,
                    'mayo': 1.341, 'junio': 1.083, 'julio': 1.289, 'agosto': 0.986,
                    'septiembre': 0.836, 'octubre': 0.722, 'noviembre': 0.620, 'diciembre': 0.246
                },
                volatilityMultiplier: 1.8,
                averageMonthly: 448
            },
            'skinny-green-350': {
                name: 'Skinny Green 350ml',
                shelfLife: 100,
                seasonalIndices: {
                    'enero': 1.321, 'febrero': 1.089, 'marzo': 1.156, 'abril': 1.287,
                    'mayo': 1.298, 'junio': 1.067, 'julio': 1.189, 'agosto': 0.934,
                    'septiembre': 0.798, 'octubre': 0.689, 'noviembre': 0.572, 'diciembre': 0.600
                },
                volatilityMultiplier: 1.5,
                averageMonthly: 73
            },
            'greenergy-480': {
                name: 'Greenergy 480ml',
                shelfLife: 80,
                seasonalIndices: {
                    'enero': 1.553, 'febrero': 1.143, 'marzo': 1.116, 'abril': 1.257,
                    'mayo': 1.367, 'junio': 1.121, 'julio': 1.226, 'agosto': 1.006,
                    'septiembre': 0.698, 'octubre': 0.710, 'noviembre': 0.587, 'diciembre': 0.216
                },
                volatilityMultiplier: 1.8,
                averageMonthly: 407
            },
            'greenergy-350': {
                name: 'Greenergy 350ml',
                shelfLife: 100,
                seasonalIndices: {
                    'enero': 1.234, 'febrero': 1.067, 'marzo': 1.034, 'abril': 1.189,
                    'mayo': 1.234, 'junio': 1.089, 'julio': 1.156, 'agosto': 0.967,
                    'septiembre': 0.734, 'octubre': 0.723, 'noviembre': 0.634, 'diciembre': 0.139
                },
                volatilityMultiplier: 1.5,
                averageMonthly: 67
            },
            'unbeetable-480': {
                name: 'Unbeetable 480ml',
                shelfLife: 80,
                seasonalIndices: {
                    'enero': 1.493, 'febrero': 1.153, 'marzo': 1.052, 'abril': 1.112,
                    'mayo': 1.298, 'junio': 1.172, 'julio': 1.295, 'agosto': 1.032,
                    'septiembre': 0.810, 'octubre': 0.699, 'noviembre': 0.606, 'diciembre': 0.278
                },
                volatilityMultiplier: 1.8,
                averageMonthly: 377
            },
            'unbeetable-350': {
                name: 'Unbeetable 350ml',
                shelfLife: 100,
                seasonalIndices: {
                    'enero': 1.378, 'febrero': 1.089, 'marzo': 0.989, 'abril': 1.067,
                    'mayo': 1.234, 'junio': 1.156, 'julio': 1.267, 'agosto': 1.012,
                    'septiembre': 0.834, 'octubre': 0.734, 'noviembre': 0.623, 'diciembre': 0.317
                },
                volatilityMultiplier: 1.5,
                averageMonthly: 89
            },
            'pinebliss-480': {
                name: 'Pinebliss 480ml',
                shelfLife: 120,
                seasonalIndices: {
                    'enero': 1.563, 'febrero': 1.260, 'marzo': 1.061, 'abril': 1.125,
                    'mayo': 1.286, 'junio': 1.257, 'julio': 1.167, 'agosto': 0.906,
                    'septiembre': 0.822, 'octubre': 0.702, 'noviembre': 0.611, 'diciembre': 0.240
                },
                volatilityMultiplier: 1.8,
                averageMonthly: 302
            },
            'pinebliss-350': {
                name: 'Pinebliss 350ml',
                shelfLife: 120,
                seasonalIndices: {
                    'enero': 1.445, 'febrero': 1.189, 'marzo': 1.034, 'abril': 1.089,
                    'mayo': 1.223, 'junio': 1.198, 'julio': 1.123, 'agosto': 0.934,
                    'septiembre': 0.856, 'octubre': 0.723, 'noviembre': 0.634, 'diciembre': 0.252
                },
                volatilityMultiplier: 1.5,
                averageMonthly: 123
            },
            'vitality-mylk-480': {
                name: 'Vitality Mylk 480ml',
                shelfLife: 20,
                seasonalIndices: {
                    'enero': 1.234, 'febrero': 1.067, 'marzo': 0.923, 'abril': 0.989,
                    'mayo': 1.034, 'junio': 0.978, 'julio': 0.934, 'agosto': 0.889,
                    'septiembre': 1.012, 'octubre': 0.945, 'noviembre': 0.834, 'diciembre': 0.661
                },
                volatilityMultiplier: 0.9,
                averageMonthly: 287
            },
            'coco-dream-480': {
                name: 'Coco Dream 480ml',
                shelfLife: 20,
                seasonalIndices: {
                    'enero': 1.189, 'febrero': 1.034, 'marzo': 0.889, 'abril': 0.934,
                    'mayo': 0.978, 'junio': 0.923, 'julio': 0.889, 'agosto': 0.834,
                    'septiembre': 0.978, 'octubre': 0.889, 'noviembre': 0.778, 'diciembre': 0.684
                },
                volatilityMultiplier: 0.9,
                averageMonthly: 156
            },
            'chokonut-480': {
                name: 'Chokonut 480ml',
                shelfLife: 25,
                seasonalIndices: {
                    'enero': 1.267, 'febrero': 1.089, 'marzo': 0.945, 'abril': 0.978,
                    'mayo': 1.012, 'junio': 0.967, 'julio': 0.923, 'agosto': 0.889,
                    'septiembre': 1.034, 'octubre': 0.978, 'noviembre': 0.856, 'diciembre': 0.762
                },
                volatilityMultiplier: 1.0,
                averageMonthly: 198
            },
            'coco-blast-480': {
                name: 'Coco Blast 480ml',
                shelfLife: 65,
                seasonalIndices: {
                    'enero': 1.345, 'febrero': 1.156, 'marzo': 1.023, 'abril': 1.089,
                    'mayo': 1.198, 'junio': 1.134, 'julio': 1.067, 'agosto': 0.978,
                    'septiembre': 0.889, 'octubre': 0.823, 'noviembre': 0.734, 'diciembre': 0.564
                },
                volatilityMultiplier: 1.3,
                averageMonthly: 234
            },
            'spicy-limonata-480': {
                name: 'Spicy Limonata 480ml',
                shelfLife: 120,
                seasonalIndices: {
                    'enero': 1.434, 'febrero': 1.198, 'marzo': 1.067, 'abril': 1.134,
                    'mayo': 1.267, 'junio': 1.289, 'julio': 1.198, 'agosto': 0.945,
                    'septiembre': 0.823, 'octubre': 0.712, 'noviembre': 0.598, 'diciembre': 0.334
                },
                volatilityMultiplier: 1.7,
                averageMonthly: 189
            },
            'c-master-480': {
                name: 'C-Master 480ml',
                shelfLife: 70,
                seasonalIndices: {
                    'enero': 1.567, 'febrero': 1.289, 'marzo': 1.098, 'abril': 1.156,
                    'mayo': 1.234, 'junio': 1.189, 'julio': 1.134, 'agosto': 1.023,
                    'septiembre': 0.867, 'octubre': 0.734, 'noviembre': 0.612, 'diciembre': 0.297
                },
                volatilityMultiplier: 1.9,
                averageMonthly: 267
            },
            'black-magic-480': {
                name: 'Black Magic 480ml',
                shelfLife: 135,
                seasonalIndices: {
                    'enero': 1.398, 'febrero': 1.167, 'marzo': 1.034, 'abril': 1.089,
                    'mayo': 1.189, 'junio': 1.156, 'julio': 1.098, 'agosto': 0.934,
                    'septiembre': 0.812, 'octubre': 0.698, 'noviembre': 0.587, 'diciembre': 0.338
                },
                volatilityMultiplier: 1.6,
                averageMonthly: 156
            },
            'tropik-glow-480': {
                name: 'Tropik Glow 480ml',
                shelfLife: 70,
                seasonalIndices: {
                    'enero': 1.489, 'febrero': 1.234, 'marzo': 1.078, 'abril': 1.134,
                    'mayo': 1.267, 'junio': 1.198, 'julio': 1.156, 'agosto': 1.012,
                    'septiembre': 0.834, 'octubre': 0.712, 'noviembre': 0.598, 'diciembre': 0.287
                },
                volatilityMultiplier: 1.8,
                averageMonthly: 198
            },
            'gingerlicious-50': {
                name: 'Gingerlicious 50ml',
                shelfLife: 150,
                seasonalIndices: {
                    'enero': 1.167, 'febrero': 1.456, 'marzo': 0.834, 'abril': 1.289,
                    'mayo': 1.123, 'junio': 1.398, 'julio': 1.067, 'agosto': 0.978,
                    'septiembre': 0.823, 'octubre': 0.678, 'noviembre': 0.845, 'diciembre': 0.342
                },
                volatilityMultiplier: 1.7,
                averageMonthly: 345
            },
            'gingerlicious-250': {
                name: 'Gingerlicious 250ml',
                shelfLife: 120,
                seasonalIndices: {
                    'enero': 1.289, 'febrero': 1.378, 'marzo': 0.923, 'abril': 1.198,
                    'mayo': 1.156, 'junio': 1.267, 'julio': 1.089, 'agosto': 0.945,
                    'septiembre': 0.789, 'octubre': 0.634, 'noviembre': 0.798, 'diciembre': 0.534
                },
                volatilityMultiplier: 1.5,
                averageMonthly: 89
            }
        };

        function analyzeProduct() {
            const productSelect = document.getElementById('productSelect');
            const productAlert = document.getElementById('productAlert');
            const selectedProduct = productSelect.value;
            
            if (!selectedProduct) {
                productAlert.innerHTML = '';
                return;
            }
            
            const product = productDatabase[selectedProduct];
            if (!product) {
                productAlert.innerHTML = '<div class="product-alert alert-danger">❌ Producto no encontrado en la base de datos</div>';
                return;
            }
            
            let alertClass = 'alert-info';
            let alertIcon = '💡';
            let shelfLifeMessage = '';
            
            if (product.shelfLife <= 25) {
                alertClass = 'alert-danger';
                alertIcon = '⚠️';
                shelfLifeMessage = ' - VIDA ÚTIL CRÍTICA: Requiere rotación muy rápida';
            } else if (product.shelfLife <= 75) {
                alertClass = 'alert-warning';
                alertIcon = '⚡';
                shelfLifeMessage = ' - Vida útil moderada: Buena rotación necesaria';
            } else {
                alertClass = 'alert-success';
                alertIcon = '✅';
                shelfLifeMessage = ' - Vida útil extendida: Menor presión de rotación';
            }
            
            productAlert.innerHTML = `
                <div class="product-alert ${alertClass}">
                    ${alertIcon} <strong>${product.name}</strong><br>
                    Vida útil: ${product.shelfLife} días${shelfLifeMessage}<br>
                    Volatilidad: ${product.volatilityMultiplier}x (${product.volatilityMultiplier > 1.5 ? 'Alta' : product.volatilityMultiplier > 1.0 ? 'Media' : 'Baja'})
                </div>
            `;
        }

        function updateSeasonalInfo() {
            const productSelect = document.getElementById('productSelect');
            const targetMonth = document.getElementById('targetMonth');
            
            if (!productSelect.value || !targetMonth.value) return;
            
            const product = productDatabase[productSelect.value];
            const seasonalFactor = product.seasonalIndices[targetMonth.value];
            
            let seasonalMessage = '';
            if (seasonalFactor > 1.3) {
                seasonalMessage = '🔥 TEMPORADA ALTA: Demanda muy elevada esperada';
            } else if (seasonalFactor > 1.1) {
                seasonalMessage = '📈 Temporada buena: Demanda por encima del promedio';
            } else if (seasonalFactor > 0.9) {
                seasonalMessage = '📊 Temporada normal: Demanda estándar';
            } else if (seasonalFactor > 0.6) {
                seasonalMessage = '📉 Temporada baja: Demanda reducida';
            } else {
                seasonalMessage = '❄️ TEMPORADA MUY BAJA: Demanda mínima';
            }
            
            const productAlert = document.getElementById('productAlert');
            productAlert.innerHTML += `
                <div class="product-alert alert-info" style="margin-top: 10px;">
                    📅 <strong>${targetMonth.value.charAt(0).toUpperCase() + targetMonth.value.slice(1)}</strong>: Factor ${seasonalFactor.toFixed(3)}<br>
                    ${seasonalMessage}
                </div>
            `;
        }

        function calculateWithSeasonalNormalization() {
            // Validación de inputs
            const productSelect = document.getElementById('productSelect').value;
            const targetMonth = document.getElementById('targetMonth').value;
            const month1 = parseFloat(document.getElementById('month1').value) || 0;
            const month2 = parseFloat(document.getElementById('month2').value) || 0;
            const month3 = parseFloat(document.getElementById('month3').value) || 0;
            const month1Type = document.getElementById('month1Type').value;
            const month2Type = document.getElementById('month2Type').value;
            const month3Type = document.getElementById('month3Type').value;
            const currentStock = parseFloat(document.getElementById('currentStock').value) || 0;
            
            if (!productSelect || !targetMonth) {
                alert('Por favor selecciona un producto y el mes objetivo');
                return;
            }
            
            if (month1 === 0 && month2 === 0 && month3 === 0) {
                alert('Por favor ingresa al menos un valor de ventas');
                return;
            }

            if (!month1Type && month1 > 0) {
                alert('Por favor selecciona qué mes fue el Mes 1');
                return;
            }
            if (!month2Type && month2 > 0) {
                alert('Por favor selecciona qué mes fue el Mes 2');
                return;
            }
            if (!month3Type && month3 > 0) {
                alert('Por favor selecciona qué mes fue el Mes 3');
                return;
            }
            
            const product = productDatabase[productSelect];
            if (!product) {
                alert('Producto no encontrado en la base de datos');
                return;
            }
            
            // Normalización estacional por producto
            let month1Normalized = 0, month2Normalized = 0, month3Normalized = 0;
            let month1Factor = 1, month2Factor = 1, month3Factor = 1;
            
            if (month1 > 0 && month1Type) {
                month1Factor = product.seasonalIndices[month1Type];
                month1Normalized = month1 / month1Factor;
            }
            
            if (month2 > 0 && month2Type) {
                month2Factor = product.seasonalIndices[month2Type];
                month2Normalized = month2 / month2Factor;
            }
            
            if (month3 > 0 && month3Type) {
                month3Factor = product.seasonalIndices[month3Type];
                month3Normalized = month3 / month3Factor;
            }
            
            // Promedio ponderado de valores NORMALIZADOS (50%, 30%, 20%)
            const normalizedWeightedAverage = (month1Normalized * 0.2) + (month2Normalized * 0.3) + (month3Normalized * 0.5);
            
            // Promedio simple SIN normalizar (para comparación)
            const simpleWeightedAverage = (month1 * 0.2) + (month2 * 0.3) + (month3 * 0.5);
            
            // Factor estacional del mes objetivo
            const targetSeasonalFactor = product.seasonalIndices[targetMonth];
            
            // Demanda estacional final = demanda base normalizada × factor estacional objetivo
            const normalizedSeasonalDemand = Math.round(normalizedWeightedAverage * targetSeasonalFactor);
            const simpleSeasonalDemand = Math.round(simpleWeightedAverage * targetSeasonalFactor);
            
            // Stock de seguridad basado en demanda normalizada
            const baseStockSafety = Math.round(normalizedWeightedAverage * 0.3);
            const adjustedStockSafety = Math.round(baseStockSafety * product.volatilityMultiplier);
            
            // Stock de seguridad método simple (para comparación)
            const simpleStockSafety = Math.round((simpleWeightedAverage * 0.3) * product.volatilityMultiplier);
            
            // Demanda total sin restricciones
            const totalDemandNormalized = normalizedSeasonalDemand + adjustedStockSafety;
            const totalDemandSimple = simpleSeasonalDemand + simpleStockSafety;
            
            // Control por vida útil
            const dailyDemand = normalizedSeasonalDemand / 30;
            const maxByShelfLife = Math.floor(dailyDemand * product.shelfLife * 0.85);
            const shelfLifeLimited = Math.min(totalDemandNormalized, maxByShelfLife);
            
            // Ajuste por stock actual
            const finalRecommendation = Math.max(0, shelfLifeLimited - currentStock);
            
            // Cálculos de cobertura
            const coverageDays = Math.round((finalRecommendation + currentStock) / dailyDemand);
            
            // Análisis de tendencia (usando datos normalizados)
            let trend = 'stable';
            let trendMessage = '📊 Demanda Estable';
            const trendValue = (month3Normalized - month1Normalized) / month1Normalized;
            
            if (trendValue > 0.15) {
                trend = 'up';
                trendMessage = '📈 Tendencia Creciente (+' + (trendValue * 100).toFixed(1) + '%)';
            } else if (trendValue < -0.15) {
                trend = 'down';
                trendMessage = '📉 Tendencia Decreciente (' + (trendValue * 100).toFixed(1) + '%)';
            }
            
            // Mostrar resultados
            document.getElementById('results').style.display = 'block';
            document.getElementById('recommendedOrder').textContent = finalRecommendation;
            document.getElementById('normalizedBaseDemand').textContent = Math.round(normalizedWeightedAverage);
            document.getElementById('seasonalDemand').textContent = normalizedSeasonalDemand;
            document.getElementById('seasonalFactor').textContent = targetSeasonalFactor.toFixed(3);
            document.getElementById('safetyStock').textContent = adjustedStockSafety;
            document.getElementById('stockAdjustment').textContent = `-${currentStock}`;
            document.getElementById('coverageDays').textContent = `${coverageDays} días`;
            
            // Highlight de normalización
            const normalizationHighlight = document.getElementById('normalizationHighlight');
            const normalizationDetails = document.getElementById('normalizationDetails');
            
            normalizationHighlight.style.display = 'block';
            let normalizationText = '';
            if (month1 > 0) normalizationText += `Mes 1: ${month1} ÷ ${month1Factor.toFixed(3)} = ${month1Normalized.toFixed(0)}<br>`;
            if (month2 > 0) normalizationText += `Mes 2: ${month2} ÷ ${month2Factor.toFixed(3)} = ${month2Normalized.toFixed(0)}<br>`;
            if (month3 > 0) normalizationText += `Mes 3: ${month3} ÷ ${month3Factor.toFixed(3)} = ${month3Normalized.toFixed(0)}<br>`;
            normalizationText += `Promedio normalizado: ${Math.round(normalizedWeightedAverage)} (vs sin normalizar: ${Math.round(simpleWeightedAverage)})`;
            
            normalizationDetails.innerHTML = normalizationText;
            
            // Tabla de comparación
            const comparisonTable = document.getElementById('comparisonTable');
            const comparisonTableBody = document.getElementById('comparisonTableBody');
            comparisonTable.style.display = 'block';
            
            const difference = finalRecommendation - Math.max(0, Math.min(totalDemandSimple, maxByShelfLife) - currentStock);
            const differencePercent = difference !== 0 ? ((difference / Math.max(1, Math.abs(Math.max(0, Math.min(totalDemandSimple, maxByShelfLife) - currentStock)))) * 100).toFixed(1) : '0';
            
            comparisonTableBody.innerHTML = `
                <tr>
                    <td>Sin Normalizar</td>
                    <td>${Math.round(simpleWeightedAverage)}</td>
                    <td>${simpleSeasonalDemand}</td>
                    <td>${totalDemandSimple}</td>
                    <td>Base de comparación</td>
                </tr>
                <tr style="background: #e8f5e8;">
                    <td><strong>CON Normalización v4.2</strong></td>
                    <td><strong>${Math.round(normalizedWeightedAverage)}</strong></td>
                    <td><strong>${normalizedSeasonalDemand}</strong></td>
                    <td><strong>${totalDemandNormalized}</strong></td>
                    <td><strong>${difference > 0 ? '+' : ''}${difference} (${difference > 0 ? '+' : ''}${differencePercent}%)</strong></td>
                </tr>
            `;
            
            // Advertencia de vida útil
            const shelfLifeWarning = document.getElementById('shelfLifeWarning');
            const shelfLifeDetails = document.getElementById('shelfLifeDetails');
            
            if (totalDemandNormalized > maxByShelfLife) {
                shelfLifeWarning.style.display = 'block';
                shelfLifeDetails.innerHTML = `
                    La demanda normalizada (${totalDemandNormalized}) excede lo que puedes vender en ${product.shelfLife} días.
                    <br>Cantidad máxima segura: ${maxByShelfLife} unidades
                    <br>Cantidad reducida: ${totalDemandNormalized - maxByShelfLife} unidades
                `;
            } else {
                shelfLifeWarning.style.display = 'none';
            }
            
            // Descripción final
            const finalOrderDescription = document.getElementById('finalOrderDescription');
            if (currentStock > 0) {
                finalOrderDescription.textContent = `Con normalización estacional v4.2 - descontando ${currentStock} unidades de stock`;
            } else {
                finalOrderDescription.textContent = 'Con normalización estacional + todas las mejoras v4.2';
            }
            
            // Tendencia
            document.getElementById('trendIndicator').innerHTML = `
                <span class="trend-indicator trend-${trend}">${trendMessage}</span>
            `;
            
            // Explicación paso a paso DETALLADA
            const calculationSteps = document.getElementById('calculationSteps');
            calculationSteps.innerHTML = `
                <div class="calculation-step">
                    <strong>1. Normalización Estacional por Producto:</strong><br>
                    ${month1 > 0 ? `Mes 1 (${month1Type}): ${month1} ÷ ${month1Factor.toFixed(3)} = ${month1Normalized.toFixed(0)}<br>` : ''}
                    ${month2 > 0 ? `Mes 2 (${month2Type}): ${month2} ÷ ${month2Factor.toFixed(3)} = ${month2Normalized.toFixed(0)}<br>` : ''}
                    ${month3 > 0 ? `Mes 3 (${month3Type}): ${month3} ÷ ${month3Factor.toFixed(3)} = ${month3Normalized.toFixed(0)}<br>` : ''}
                    <em>Cada mes se divide por su factor estacional específico de ${product.name}</em>
                </div>
                <div class="calculation-step">
                    <strong>2. Promedio Ponderado Normalizado:</strong><br>
                    (${month1Normalized.toFixed(0)} × 20%) + (${month2Normalized.toFixed(0)} × 30%) + (${month3Normalized.toFixed(0)} × 50%) = ${Math.round(normalizedWeightedAverage)} unidades<br>
                    <em>Sin normalizar habría sido: ${Math.round(simpleWeightedAverage)} unidades</em>
                </div>
                <div class="calculation-step">
                    <strong>3. Aplicación del Factor Estacional Objetivo:</strong><br>
                    ${Math.round(normalizedWeightedAverage)} × ${targetSeasonalFactor.toFixed(3)} (${targetMonth}) = ${normalizedSeasonalDemand} unidades
                </div>
                <div class="calculation-step">
                    <strong>4. Stock de Seguridad Normalizado:</strong><br>
                    ${Math.round(normalizedWeightedAverage)} × 30% × ${product.volatilityMultiplier} = ${adjustedStockSafety} unidades
                </div>
                <div class="calculation-step">
                    <strong>5. Demanda Total Normalizada:</strong><br>
                    ${normalizedSeasonalDemand} + ${adjustedStockSafety} = ${totalDemandNormalized} unidades
                </div>
                <div class="calculation-step">
                    <strong>6. Control de Vida Útil:</strong><br>
                    Máximo por ${product.shelfLife} días: ${maxByShelfLife} unidades<br>
                    Resultado: ${shelfLifeLimited} unidades
                </div>
                <div class="calculation-step">
                    <strong>7. Ajuste Final por Stock:</strong><br>
                    ${shelfLifeLimited} - ${currentStock} = <strong>${finalRecommendation} unidades</strong><br>
                    <em>Diferencia vs sin normalizar: ${difference > 0 ? '+' : ''}${difference} unidades (${difference > 0 ? '+' : ''}${differencePercent}%)</em>
                </div>
                <div class="calculation-step">
                    <strong>8. Cobertura Proyectada:</strong><br>
                    (${finalRecommendation} + ${currentStock}) ÷ ${dailyDemand.toFixed(1)} unidades/día = ${coverageDays} días
                </div>
            `;
            
            // Scroll suave hacia resultados
            document.getElementById('results').scrollIntoView({ 
                behavior: 'smooth', 
                block: 'start' 
            });
        }
    </script>
</body>
</html>
