<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora v6.0 - Reset Juice | Datos Reales</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #81C784 0%, #4CAF50 50%, #388E3C 100%);
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 25px 50px rgba(56, 142, 60, 0.15);
            overflow: hidden;
        }
        
        .header {
            background: linear-gradient(135deg, #4CAF50, #66BB6A);
            color: white;
            padding: 30px;
            text-align: center;
            position: relative;
        }
        
        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="50" cy="50" r="2" fill="rgba(255,255,255,0.1)"/></svg>') repeat;
            background-size: 30px 30px;
        }
        
        .header h1 {
            font-size: 2.8em;
            margin-bottom: 10px;
            font-weight: 300;
            position: relative;
            z-index: 1;
        }
        
        .header p {
            font-size: 1.2em;
            opacity: 0.95;
            position: relative;
            z-index: 1;
        }
        
        .version-badge {
            background: rgba(255,255,255,0.25);
            padding: 8px 20px;
            border-radius: 25px;
            font-size: 0.9em;
            margin-top: 15px;
            display: inline-block;
            position: relative;
            z-index: 1;
            border: 1px solid rgba(255,255,255,0.3);
        }
        
        .reset-badge {
            background: #2E7D32;
            color: white;
            padding: 5px 12px;
            border-radius: 15px;
            font-size: 0.8em;
            margin-left: 10px;
            font-weight: bold;
        }
        
        .content {
            padding: 30px;
        }
        
        .product-insight {
            background: linear-gradient(135deg, #C8E6C9, #A5D6A7);
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 30px;
            border-left: 5px solid #4CAF50;
            box-shadow: 0 5px 15px rgba(76, 175, 80, 0.1);
        }
        
        .product-insight h3 {
            color: #2E7D32;
            margin-bottom: 15px;
            font-size: 1.4em;
        }
        
        .product-insight p {
            color: #1B5E20;
            line-height: 1.6;
        }
        
        .form-section {
            background: #F1F8E9;
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 30px;
            border: 2px solid #C8E6C9;
            transition: border-color 0.3s ease;
        }
        
        .form-section:hover {
            border-color: #81C784;
        }
        
        .form-section h3 {
            color: #2E7D32;
            margin-bottom: 20px;
            font-size: 1.4em;
            border-bottom: 3px solid #4CAF50;
            padding-bottom: 10px;
        }
        
        .input-group {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .input-field {
            display: flex;
            flex-direction: column;
        }
        
        .input-field label {
            font-weight: 600;
            color: #2E7D32;
            margin-bottom: 8px;
            font-size: 1em;
        }
        
        .input-field input, .input-field select {
            padding: 15px;
            border: 2px solid #C8E6C9;
            border-radius: 10px;
            font-size: 1em;
            transition: all 0.3s ease;
            background: white;
        }
        
        .input-field input:focus, .input-field select:focus {
            outline: none;
            border-color: #4CAF50;
            box-shadow: 0 0 0 4px rgba(76, 175, 80, 0.1);
            transform: translateY(-1px);
        }
        
        .shelf-life-info {
            background: #E8F5E8;
            border: 2px solid #A5D6A7;
            border-radius: 10px;
            padding: 15px;
            margin-top: 15px;
            color: #1B5E20;
        }
        
        .shelf-life-warning {
            background: #FFF3E0;
            border: 2px solid #FFB74D;
            border-radius: 10px;
            padding: 15px;
            margin-top: 15px;
            color: #E65100;
            font-weight: 600;
        }
        
        .shelf-life-danger {
            background: #FFEBEE;
            border: 2px solid #EF5350;
            border-radius: 10px;
            padding: 15px;
            margin-top: 15px;
            color: #C62828;
            font-weight: 600;
        }
        
        .calculate-btn {
            background: linear-gradient(135deg, #4CAF50, #66BB6A);
            color: white;
            border: none;
            padding: 18px 45px;
            font-size: 1.2em;
            font-weight: 600;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
            margin: 25px auto;
            display: block;
            box-shadow: 0 8px 25px rgba(76, 175, 80, 0.3);
        }
        
        .calculate-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 35px rgba(76, 175, 80, 0.4);
            background: linear-gradient(135deg, #66BB6A, #81C784);
        }
        
        .calculate-btn:active {
            transform: translateY(-1px);
        }
        
        .results {
            display: none;
            background: white;
            padding: 35px;
            border-radius: 15px;
            margin-top: 30px;
            border: 3px solid #4CAF50;
            box-shadow: 0 15px 40px rgba(76, 175, 80, 0.15);
        }
        
        .results h3 {
            color: #2E7D32;
            margin-bottom: 30px;
            font-size: 1.8em;
            text-align: center;
            border-bottom: 2px solid #C8E6C9;
            padding-bottom: 15px;
        }
        
        .result-card {
            background: white;
            padding: 25px;
            border-radius: 12px;
            margin-bottom: 20px;
            box-shadow: 0 8px 20px rgba(76, 175, 80, 0.1);
            border-left: 5px solid #81C784;
            border: 1px solid #E8F5E8;
            transition: transform 0.3s ease;
        }
        
        .result-card:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 30px rgba(76, 175, 80, 0.15);
        }
        
        .result-main {
            border-left-color: #4CAF50;
            background: linear-gradient(135deg, #F1F8E9, #E8F5E8);
            border: 2px solid #4CAF50;
        }
        
        .result-card h4 {
            color: #2E7D32;
            margin-bottom: 12px;
            font-size: 1.2em;
        }
        
        .result-value {
            font-size: 2em;
            font-weight: bold;
            color: #2E7D32;
        }
        
        .result-range {
            font-size: 2em;
            font-weight: bold;
            color: #4CAF50;
        }
        
        .range-explanation {
            font-size: 0.9em;
            color: #558B2F;
            margin-top: 8px;
            font-style: italic;
        }
        
        .shelf-life-alert {
            background: #FFF3E0;
            border: 2px solid #FFB74D;
            border-radius: 12px;
            padding: 20px;
            margin: 20px 0;
            color: #E65100;
        }
        
        .calculation-details {
            background: #F1F8E9;
            padding: 25px;
            border-radius: 12px;
            margin-top: 25px;
            border: 1px solid #C8E6C9;
        }
        
        .calculation-step {
            margin-bottom: 20px;
            padding: 20px;
            background: white;
            border-radius: 8px;
            border-left: 4px solid #4CAF50;
            box-shadow: 0 3px 10px rgba(76, 175, 80, 0.1);
        }
        
        .step-title {
            font-weight: bold;
            color: #2E7D32;
            margin-bottom: 10px;
            font-size: 1.1em;
        }
        
        .step-formula {
            font-family: 'Courier New', monospace;
            background: #E8F5E8;
            padding: 8px 12px;
            border-radius: 5px;
            margin: 8px 0;
            display: inline-block;
            color: #1B5E20;
        }
        
        .step-result {
            color: #2E7D32;
            font-weight: bold;
            margin-top: 8px;
        }
        
        .trend-analysis {
            margin-top: 25px;
            text-align: center;
        }
        
        .trend-indicator {
            display: inline-block;
            padding: 12px 25px;
            border-radius: 25px;
            font-weight: bold;
            margin: 10px;
        }
        
        .trend-up {
            background: #C8E6C9;
            color: #1B5E20;
            border: 2px solid #4CAF50;
        }
        
        .trend-down {
            background: #FFCDD2;
            color: #C62828;
            border: 2px solid #F44336;
        }
        
        .trend-stable {
            background: #FFF3E0;
            color: #E65100;
            border: 2px solid #FF9800;
        }
        
        .methodology {
            background: #E8F5E8;
            padding: 25px;
            border-radius: 12px;
            margin-top: 30px;
            border: 2px solid #A5D6A7;
        }
        
        .methodology h4 {
            color: #1B5E20;
            margin-bottom: 20px;
            font-size: 1.3em;
        }
        
        .methodology ul {
            color: #2E7D32;
            margin-left: 25px;
        }
        
        .methodology li {
            margin-bottom: 10px;
            line-height: 1.5;
        }
        
        .error {
            background: #FFEBEE;
            color: #C62828;
            padding: 15px;
            border-radius: 8px;
            margin: 15px 0;
            border: 2px solid #EF5350;
        }
        
        .data-source-badge {
            background: linear-gradient(135deg, #2E7D32, #388E3C);
            color: white;
            padding: 10px 20px;
            border-radius: 20px;
            font-size: 0.9em;
            margin: 15px 0;
            display: inline-block;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🧃 Reset Juice | Calculadora Inteligente</h1>
            <p>Predicción de demanda con datos históricos reales y análisis estacional personalizado</p>
            <div class="version-badge">
                ✨ Versión 6.0 - Datos Reales
                <span class="reset-badge">RESET JUICE</span>
            </div>
        </div>
        
        <div class="content">
            <div class="product-insight">
                <h3>📊 Alimentado por Datos Reales de Reset Juice</h3>
                <p><strong>Precisión científica:</strong> Esta calculadora utiliza tus datos históricos reales de ventas 2023-2025, con índices estacionales calculados específicamente para cada producto y presentación de Reset Juice. Optimizada para minimizar mermas y maximizar disponibilidad.</p>
                <div class="data-source-badge">📈 Basado en 1,908 registros reales de ventas</div>
            </div>
            
            <div class="form-section">
                <h3>🧃 Selección de Producto Reset</h3>
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
                <h3>📈 Ventas de los Últimos 3 Meses</h3>
                <div class="input-group">
                    <div class="input-field">
                        <label for="month1">Mes 1 (más antiguo)</label>
                        <input type="number" id="month1" placeholder="Ej: 126" min="0">
                    </div>
                    <div class="input-field">
                        <label for="month2">Mes 2</label>
                        <input type="number" id="month2" placeholder="Ej: 80" min="0">
                    </div>
                    <div class="input-field">
                        <label for="month3">Mes 3 (más reciente)</label>
                        <input type="number" id="month3" placeholder="Ej: 132" min="0">
                    </div>
                </div>
            </div>
            
            <button class="calculate-btn" onclick="calculatePersonalizedOrder()">🧃 Calcular Orden Reset</button>
            
            <div id="results" class="results">
                <h3>📋 Recomendación Reset Juice</h3>
                
                <div class="result-card result-main">
                    <h4>🎯 RANGO RECOMENDADO</h4>
                    <div class="result-range" id="recommendedRange">--</div>
                    <p class="range-explanation">Rango óptimo basado en datos reales de Reset Juice</p>
                </div>
                
                <div id="shelfLifeAlert" class="shelf-life-alert" style="display: none;">
                    <h5>⏰ Limitación por Vida Útil</h5>
                    <div id="shelfLifeMessage">--</div>
                </div>
                
                <div class="result-card">
                    <h4>📊 Demanda Base (Datos Reales)</h4>
                    <div class="result-value" id="baseDemand">--</div>
                    <p>Promedio ponderado: Reciente (50%) + Medio (30%) + Antiguo (20%)</p>
                </div>
                
                <div class="result-card">
                    <h4>🌟 Demanda Estacional Reset</h4>
                    <div class="result-value" id="seasonalDemand">--</div>
                    <p>Basada en historial real de ventas 2023-2025</p>
                </div>
                
                <div class="result-card">
                    <h4>📈 Factor Estacional Real</h4>
                    <div class="result-value" id="seasonalFactor">--</div>
                    <p>Calculado con datos históricos de Reset Juice</p>
                </div>
                
                <div class="result-card">
                    <h4>🛡️ Stock de Seguridad</h4>
                    <div class="result-value" id="safetyStock">--</div>
                    <p id="safetyStockDescription">Basado en volatilidad real del producto</p>
                </div>
                
                <div class="result-card">
                    <h4>⏱️ Máximo Vendible (Vida Útil)</h4>
                    <div class="result-value" id="maxSellable">--</div>
                    <p id="maxSellableDescription">Límite por días de caducidad del producto</p>
                </div>
                
                <div class="result-card">
                    <h4>📅 Días de Cobertura</h4>
                    <div class="result-value" id="coverageDays">--</div>
                    <p>Duración estimada del inventario recomendado</p>
                </div>
                
                <div class="trend-analysis">
                    <h4>📈 Análisis de Tendencia</h4>
                    <div id="trendIndicator">--</div>
                </div>
                
                <div class="calculation-details">
                    <h4>🔢 Cálculos Detallados con Datos Reales</h4>
                    <div id="calculationSteps">--</div>
                </div>
            </div>
            
            <div class="methodology">
                <h4>🧃 Metodología v6.0: Reset Juice con Datos Reales</h4>
                <ul>
                    <li><strong>📊 Datos 100% Reales:</strong> Basado en 1,908 registros reales de ventas Reset Juice 2023-2025</li>
                    <li><strong>🎯 Índices Específicos:</strong> Cada producto tiene índices estacionales calculados con SUS datos</li>
                    <li><strong>⚖️ Volatilidad Real:</strong> Multiplicadores basados en variabilidad histórica de cada producto</li>
                    <li><strong>⏱️ Control de Vida Útil:</strong> Previene recomendaciones que generen mermas</li>
                    <li><strong>📈 Promedio Ponderado:</strong> Mayor peso al mes más reciente (50%-30%-20%)</li>
                    <li><strong>🔍 Transparencia Total:</strong> Explicación paso a paso de cada cálculo</li>
                </ul>
            </div>
        </div>
    </div>

    <script>
        // Base de datos REAL de Reset Juice - v6.0 con datos extraídos del Excel
        const productDatabaseReset = {
            'carrot-rush-480': {
                name: 'Carrot Rush 480ml',
                shelfLife: 75,
                seasonalIndices: {
                    'enero': 1.912, 'febrero': 1.471, 'marzo': 1.201, 'abril': 1.268,
                    'mayo': 1.294, 'junio': 1.262, 'julio': 1.220, 'agosto': 1.310,
                    'septiembre': 0.439, 'octubre': 0.372, 'noviembre': 0.222, 'diciembre': 0.029
                },
                volatilityMultiplier: 1.1,
                averageMonthly: 104
            },
            'immune-boost-50': {
                name: 'Immune Boost 50ml',
                shelfLife: 150,
                seasonalIndices: {
                    'enero': 0.983, 'febrero': 1.346, 'marzo': 0.722, 'abril': 1.181,
                    'mayo': 0.988, 'junio': 1.334, 'julio': 0.952, 'agosto': 0.919,
                    'septiembre': 1.131, 'octubre': 0.884, 'noviembre': 1.169, 'diciembre': 0.390
                },
                volatilityMultiplier: 1.1,
                averageMonthly: 530
            },
            'skinny-green-480': {
                name: 'Skinny Green 480ml',
                shelfLife: 75,
                seasonalIndices: {
                    'enero': 1.625, 'febrero': 1.243, 'marzo': 1.214, 'abril': 1.348,
                    'mayo': 1.461, 'junio': 1.186, 'julio': 1.472, 'agosto': 1.120,
                    'septiembre': 0.494, 'octubre': 0.350, 'noviembre': 0.314, 'diciembre': 0.173
                },
                volatilityMultiplier: 1.1,
                averageMonthly: 429
            },
            'skinny-green-350': {
                name: 'Skinny Green 350ml',
                shelfLife: 100,
                seasonalIndices: {
                    'enero': 1.384, 'febrero': 1.146, 'marzo': 1.222, 'abril': 1.012,
                    'mayo': 0.734, 'junio': 0.920, 'julio': 1.053, 'agosto': 1.021,
                    'septiembre': 1.301, 'octubre': 1.271, 'noviembre': 0.623, 'diciembre': 0.315
                },
                volatilityMultiplier: 1.4,
                averageMonthly: 83
            },
            'greenergy-480': {
                name: 'Greenergy 480ml',
                shelfLife: 80,
                seasonalIndices: {
                    'enero': 1.758, 'febrero': 1.293, 'marzo': 1.264, 'abril': 1.422,
                    'mayo': 1.548, 'junio': 1.269, 'julio': 1.410, 'agosto': 1.176,
                    'septiembre': 0.200, 'octubre': 0.305, 'noviembre': 0.237, 'diciembre': 0.117
                },
                volatilityMultiplier: 1.4,
                averageMonthly: 359
            },
            'greenergy-350': {
                name: 'Greenergy 350ml',
                shelfLife: 100,
                seasonalIndices: {
                    'enero': 1.391, 'febrero': 1.018, 'marzo': 1.103, 'abril': 0.968,
                    'mayo': 0.926, 'junio': 0.565, 'julio': 1.311, 'agosto': 0.934,
                    'septiembre': 1.155, 'octubre': 1.064, 'noviembre': 0.962, 'diciembre': 0.601
                },
                volatilityMultiplier: 1.4,
                averageMonthly: 83
            },
            'unbeetable-480': {
                name: 'Unbeetable 480ml',
                shelfLife: 80,
                seasonalIndices: {
                    'enero': 1.662, 'febrero': 1.269, 'marzo': 1.153, 'abril': 1.232,
                    'mayo': 1.438, 'junio': 1.294, 'julio': 1.452, 'agosto': 1.164,
                    'septiembre': 0.463, 'octubre': 0.347, 'noviembre': 0.314, 'diciembre': 0.211
                },
                volatilityMultiplier: 1.1,
                averageMonthly: 331
            },
            'unbeetable-350': {
                name: 'Unbeetable 350ml',
                shelfLife: 100,
                seasonalIndices: {
                    'enero': 1.227, 'febrero': 0.738, 'marzo': 1.484, 'abril': 0.746,
                    'mayo': 0.834, 'junio': 1.171, 'julio': 1.131, 'agosto': 1.372,
                    'septiembre': 1.324, 'octubre': 1.215, 'noviembre': 0.590, 'diciembre': 0.168
                },
                volatilityMultiplier: 1.4,
                averageMonthly: 42
            },
            'pinebliss-480': {
                name: 'Pinebliss 480ml',
                shelfLife: 120,
                seasonalIndices: {
                    'enero': 1.753, 'febrero': 1.414, 'marzo': 1.190, 'abril': 1.262,
                    'mayo': 1.443, 'junio': 1.410, 'julio': 1.321, 'agosto': 1.053,
                    'septiembre': 0.355, 'octubre': 0.307, 'noviembre': 0.257, 'diciembre': 0.234
                },
                volatilityMultiplier: 1.1,
                averageMonthly: 269
            },
            'pinebliss-350': {
                name: 'Pinebliss 350ml',
                shelfLife: 120,
                seasonalIndices: {
                    'enero': 1.303, 'febrero': 1.016, 'marzo': 1.149, 'abril': 1.381,
                    'mayo': 0.788, 'junio': 1.097, 'julio': 1.186, 'agosto': 0.854,
                    'septiembre': 0.972, 'octubre': 1.657, 'noviembre': 0.464, 'diciembre': 0.133
                },
                volatilityMultiplier: 1.7,
                averageMonthly: 45
            },
            'vitality-mylk-480': {
                name: 'Vitality Mylk 480ml',
                shelfLife: 20,
                seasonalIndices: {
                    'enero': 1.981, 'febrero': 1.232, 'marzo': 1.370, 'abril': 1.497,
                    'mayo': 1.609, 'junio': 1.166, 'julio': 1.571, 'agosto': 1.138,
                    'septiembre': 0.192, 'octubre': 0.091, 'noviembre': 0.127, 'diciembre': 0.026
                },
                volatilityMultiplier: 1.4,
                averageMonthly: 193
            },
            'coco-dream-480': {
                name: 'Coco Dream 480ml',
                shelfLife: 20,
                seasonalIndices: {
                    'enero': 1.820, 'febrero': 1.653, 'marzo': 1.228, 'abril': 1.263,
                    'mayo': 1.659, 'junio': 0.964, 'julio': 0.964, 'agosto': 1.066,
                    'septiembre': 0.458, 'octubre': 0.512, 'noviembre': 0.359, 'diciembre': 0.054
                },
                volatilityMultiplier: 1.4,
                averageMonthly: 56
            },
            'chokonut-480': {
                name: 'Chokonut 480ml',
                shelfLife: 25,
                seasonalIndices: {
                    'enero': 0.792, 'febrero': 1.271, 'marzo': 1.053, 'abril': 0.834,
                    'mayo': 1.251, 'junio': 1.115, 'julio': 1.251, 'agosto': 1.542,
                    'septiembre': 1.032, 'octubre': 0.907, 'noviembre': 0.860, 'diciembre': 0.094
                },
                volatilityMultiplier: 1.4,
                averageMonthly: 32
            },
            'coco-blast-480': {
                name: 'Coco Blast 480ml',
                shelfLife: 65,
                seasonalIndices: {
                    'enero': 0.700, 'febrero': 0.789, 'marzo': 1.291, 'abril': 1.076,
                    'mayo': 1.184, 'junio': 2.099, 'julio': 0.700, 'agosto': 1.686,
                    'septiembre': 0.592, 'octubre': 1.049, 'noviembre': 0.565, 'diciembre': 0.269
                },
                volatilityMultiplier: 1.4,
                averageMonthly: 19
            },
            'spicy-limonata-480': {
                name: 'Spicy Limonata 480ml',
                shelfLife: 120,
                seasonalIndices: {
                    'enero': 1.329, 'febrero': 1.231, 'marzo': 1.173, 'abril': 1.281,
                    'mayo': 1.589, 'junio': 1.074, 'julio': 1.358, 'agosto': 1.101,
                    'septiembre': 0.744, 'octubre': 0.387, 'noviembre': 0.394, 'diciembre': 0.340
                },
                volatilityMultiplier: 1.1,
                averageMonthly: 138
            },
            'c-master-480': {
                name: 'C-Master 480ml',
                shelfLife: 70,
                seasonalIndices: {
                    'enero': 1.834, 'febrero': 1.427, 'marzo': 1.240, 'abril': 1.150,
                    'mayo': 1.611, 'junio': 1.233, 'julio': 1.419, 'agosto': 1.028,
                    'septiembre': 0.598, 'octubre': 0.275, 'noviembre': 0.145, 'diciembre': 0.040
                },
                volatilityMultiplier: 1.4,
                averageMonthly: 186
            },
            'black-magic-480': {
                name: 'Black Magic 480ml',
                shelfLife: 135,
                seasonalIndices: {
                    'enero': 1.111, 'febrero': 1.285, 'marzo': 1.074, 'abril': 1.561,
                    'mayo': 1.243, 'junio': 1.185, 'julio': 1.375, 'agosto': 1.412,
                    'septiembre': 0.611, 'octubre': 0.603, 'noviembre': 0.460, 'diciembre': 0.079
                },
                volatilityMultiplier: 1.1,
                averageMonthly: 63
            },
            'tropik-glow-480': {
                name: 'Tropik Glow 480ml',
                shelfLife: 70,
                seasonalIndices: {
                    'enero': 1.729, 'febrero': 1.210, 'marzo': 1.253, 'abril': 1.367,
                    'mayo': 1.529, 'junio': 1.263, 'julio': 1.587, 'agosto': 1.340,
                    'septiembre': 0.217, 'octubre': 0.196, 'noviembre': 0.170, 'diciembre': 0.138
                },
                volatilityMultiplier: 1.4,
                averageMonthly: 138
            },
            'gingerlicious-50': {
                name: 'Gingerlicious 50ml',
                shelfLife: 150,
                seasonalIndices: {
                    'enero': 0.926, 'febrero': 3.046, 'marzo': 0.435, 'abril': 0.553,
                    'mayo': 1.107, 'junio': 1.608, 'julio': 0.787, 'agosto': 1.455,
                    'septiembre': 0.496, 'octubre': 0.397, 'noviembre': 0.856, 'diciembre': 0.334
                },
                volatilityMultiplier: 2.0,
                averageMonthly: 96
            },
            'gingerlicious-250': {
                name: 'Gingerlicious 250ml',
                shelfLife: 120,
                seasonalIndices: {
                    'enero': 0.108, 'febrero': 1.713, 'marzo': 1.856, 'abril': 1.804,
                    'mayo': 1.748, 'junio': 1.852, 'julio': 2.095, 'agosto': 0.204,
                    'septiembre': 0.137, 'octubre': 0.169, 'noviembre': 0.234, 'diciembre': 0.078
                },
                volatilityMultiplier: 2.0,
                averageMonthly: 77
            }
        };

        function analyzeProduct() {
            const productId = document.getElementById('productSelect').value;
            const alertDiv = document.getElementById('productAlert');
            
            if (!productId) {
                alertDiv.innerHTML = '';
                return;
            }
            
            const product = productDatabaseReset[productId];
            if (!product) {
                alertDiv.innerHTML = '<div class="error">Producto no encontrado en la base de datos.</div>';
                return;
            }
            
            // Mostrar información de vida útil con datos reales
            let alertClass = 'shelf-life-info';
            let alertMessage = `📊 <strong>${product.name}</strong><br>
                              ⏱️ Vida útil: ${product.shelfLife} días<br>
                              📈 Promedio mensual real: ${product.averageMonthly} unidades<br>
                              🎯 Volatilidad: ${product.volatilityMultiplier}x (calculada con datos reales)`;
            
            if (product.shelfLife <= 25) {
                alertClass = 'shelf-life-danger';
                alertMessage += '<br>⚠️ <strong>VIDA ÚTIL CRÍTICA</strong> - Se aplicarán límites estrictos para evitar mermas';
            } else if (product.shelfLife <= 70) {
                alertClass = 'shelf-life-warning';
                alertMessage += '<br>⚠️ <strong>VIDA ÚTIL CORTA</strong> - Se limitará la recomendación por caducidad';
            }
            
            alertDiv.innerHTML = `<div class="${alertClass}">${alertMessage}</div>`;
        }

        function updateSeasonalInfo() {
            const productId = document.getElementById('productSelect').value;
            const month = document.getElementById('targetMonth').value;
            
            if (!productId || !month) return;
            
            const product = productDatabaseReset[productId];
            const seasonalIndex = product.seasonalIndices[month];
            
            // Información adicional sobre estacionalidad real
            console.log(`Factor estacional REAL para ${product.name} en ${month}: ${seasonalIndex}`);
        }

        function calculatePersonalizedOrder() {
            // Obtener valores de entrada
            const productId = document.getElementById('productSelect').value;
            const month1 = parseFloat(document.getElementById('month1').value);
            const month2 = parseFloat(document.getElementById('month2').value);
            const month3 = parseFloat(document.getElementById('month3').value);
            const targetMonth = document.getElementById('targetMonth').value;
            
            // Validaciones
            if (!productId) {
                alert('Por favor selecciona un producto Reset Juice');
                return;
            }
            
            if (!targetMonth) {
                alert('Por favor selecciona el mes objetivo');
                return;
            }
            
            if (isNaN(month1) || isNaN(month2) || isNaN(month3)) {
                alert('Por favor ingresa las ventas de los 3 meses');
                return;
            }
            
            const product = productDatabaseReset[productId];
            
            // PASO 1: Calcular demanda base con promedio ponderado optimizado
            const weightedAverage = (month1 * 0.2) + (month2 * 0.3) + (month3 * 0.5);
            
            // PASO 2: Aplicar factor estacional REAL específico del producto
            const seasonalFactor = product.seasonalIndices[targetMonth];
            const seasonalDemand = weightedAverage * seasonalFactor;
            
            // PASO 3: Calcular stock de seguridad con volatilidad REAL
            const demandVariation = Math.sqrt(
                (Math.pow(month1 - weightedAverage, 2) + 
                 Math.pow(month2 - weightedAverage, 2) + 
                 Math.pow(month3 - weightedAverage, 2)) / 3
            );
            const safetyStockBase = demandVariation * product.volatilityMultiplier;
            
            // PASO 4: Calcular máximo vendible basado en vida útil
            const dailyDemand = seasonalDemand / 30;
            const maxSellable = dailyDemand * product.shelfLife;
            
            // PASO 5: Calcular recomendación base (sin límite de vida útil)
            const baseRecommendation = seasonalDemand + safetyStockBase;
            
            // PASO 6: Aplicar límite de vida útil
            let finalRecommendation = baseRecommendation;
            let shelfLifeLimited = false;
            
            if (baseRecommendation > maxSellable) {
                finalRecommendation = maxSellable;
                shelfLifeLimited = true;
            }
            
            // PASO 7: Calcular rango (mínimo - máximo)
            const minRecommendation = Math.max(seasonalDemand - safetyStockBase * 0.5, 0);
            const maxRecommendation = shelfLifeLimited ? maxSellable : seasonalDemand + safetyStockBase * 1.5;
            
            // PASO 8: Análisis de tendencia
            let trendAnalysis = '';
            let trendClass = '';
            
            if (month3 > month2 && month2 > month1) {
                trendAnalysis = '📈 Tendencia Creciente';
                trendClass = 'trend-up';
            } else if (month3 < month2 && month2 < month1) {
                trendAnalysis = '📉 Tendencia Decreciente';
                trendClass = 'trend-down';
            } else {
                trendAnalysis = '➡️ Tendencia Estable';
                trendClass = 'trend-stable';
            }
            
            // Mostrar resultados
            displayResults({
                weightedAverage,
                seasonalFactor,
                seasonalDemand,
                safetyStockBase,
                maxSellable,
                baseRecommendation,
                finalRecommendation,
                minRecommendation,
                maxRecommendation,
                shelfLifeLimited,
                trendAnalysis,
                trendClass,
                product,
                targetMonth,
                month1,
                month2,
                month3
            });
        }

        function displayResults(data) {
            // Mostrar sección de resultados
            document.getElementById('results').style.display = 'block';
            
            // Rango recomendado
            document.getElementById('recommendedRange').textContent = 
                `${Math.round(data.minRecommendation)} - ${Math.round(data.maxRecommendation)} unidades`;
            
            // Alertas de vida útil
            const shelfLifeAlert = document.getElementById('shelfLifeAlert');
            if (data.shelfLifeLimited) {
                shelfLifeAlert.style.display = 'block';
                document.getElementById('shelfLifeMessage').innerHTML = 
                    `⚠️ <strong>Recomendación limitada por vida útil</strong><br>
                     Recomendación original: ${Math.round(data.baseRecommendation)} unidades<br>
                     Máximo vendible en ${data.product.shelfLife} días: ${Math.round(data.maxSellable)} unidades<br>
                     <strong>Se aplicó el límite para evitar mermas por caducidad.</strong>`;
            } else {
                shelfLifeAlert.style.display = 'none';
            }
            
            // Resultados individuales
            document.getElementById('baseDemand').textContent = Math.round(data.weightedAverage);
            document.getElementById('seasonalDemand').textContent = Math.round(data.seasonalDemand);
            document.getElementById('seasonalFactor').textContent = data.seasonalFactor.toFixed(3);
            document.getElementById('safetyStock').textContent = Math.round(data.safetyStockBase);
            document.getElementById('maxSellable').textContent = Math.round(data.maxSellable);
            
            // Días de cobertura
            const dailyDemand = data.seasonalDemand / 30;
            const coverageDays = data.finalRecommendation / dailyDemand;
            document.getElementById('coverageDays').textContent = `${Math.round(coverageDays)} días`;
            
            // Tendencia
            document.getElementById('trendIndicator').innerHTML = 
                `<span class="trend-indicator ${data.trendClass}">${data.trendAnalysis}</span>`;
            
            // Cálculos paso a paso
            generateStepByStepCalculations(data);
            
            // Scroll to results
            document.getElementById('results').scrollIntoView({ behavior: 'smooth' });
        }

        function generateStepByStepCalculations(data) {
            const stepsDiv = document.getElementById('calculationSteps');
            
            const steps = `
                <div class="calculation-step">
                    <div class="step-title">1. 📊 Cálculo de Demanda Base (Promedio Ponderado)</div>
                    <div class="step-formula">
                        Mes 1 (${data.month1}) × 20% + Mes 2 (${data.month2}) × 30% + Mes 3 (${data.month3}) × 50%
                    </div>
                    <div class="step-formula">
                        ${data.month1} × 0.2 + ${data.month2} × 0.3 + ${data.month3} × 0.5 = ${data.weightedAverage.toFixed(1)}
                    </div>
                    <div class="step-result">Demanda Base: ${Math.round(data.weightedAverage)} unidades</div>
                </div>
                
                <div class="calculation-step">
                    <div class="step-title">2. 🧃 Aplicación de Factor Estacional REAL de Reset Juice</div>
                    <div class="step-formula">
                        Demanda Base × Factor Estacional Real del ${data.targetMonth}
                    </div>
                    <div class="step-formula">
                        ${data.weightedAverage.toFixed(1)} × ${data.seasonalFactor} = ${data.seasonalDemand.toFixed(1)}
                    </div>
                    <div class="step-result">Demanda Estacional: ${Math.round(data.seasonalDemand)} unidades</div>
                    <div style="font-size: 0.9em; color: #558B2F; margin-top: 5px;">
                        ✨ Basado en datos históricos reales de Reset Juice 2023-2025
                    </div>
                </div>
                
                <div class="calculation-step">
                    <div class="step-title">3. 🛡️ Cálculo de Stock de Seguridad (Volatilidad Real)</div>
                    <div class="step-formula">
                        Desviación Estándar × Multiplicador de Volatilidad Real (${data.product.volatilityMultiplier}x)
                    </div>
                    <div class="step-result">Stock de Seguridad: ${Math.round(data.safetyStockBase)} unidades</div>
                    <div style="font-size: 0.9em; color: #558B2F; margin-top: 5px;">
                        ✨ Multiplicador calculado con variabilidad histórica del producto
                    </div>
                </div>
                
                <div class="calculation-step">
                    <div class="step-title">4. ⏱️ Control de Vida Útil (Prevención de Mermas)</div>
                    <div class="step-formula">
                        Demanda Diaria × Días de Vida Útil = Máximo Vendible
                    </div>
                    <div class="step-formula">
                        ${(data.seasonalDemand / 30).toFixed(1)} × ${data.product.shelfLife} = ${data.maxSellable.toFixed(1)}
                    </div>
                    <div class="step-result">Máximo Vendible: ${Math.round(data.maxSellable)} unidades</div>
                    ${data.shelfLifeLimited ? '<div style="color: #E65100; font-weight: bold;">⚠️ Límite aplicado por vida útil para evitar mermas</div>' : ''}
                </div>
                
                <div class="calculation-step">
                    <div class="step-title">5. 🎯 Cálculo de Rango Final (Reset Juice)</div>
                    <div class="step-formula">
                        Mínimo: Demanda Estacional - (Stock Seguridad × 0.5)
                    </div>
                    <div class="step-formula">
                        Máximo: ${data.shelfLifeLimited ? 'Limitado por vida útil' : 'Demanda + (Stock Seguridad × 1.5)'}
                    </div>
                    <div class="step-result">Rango Recomendado: ${Math.round(data.minRecommendation)} - ${Math.round(data.maxRecommendation)} unidades</div>
                    <div style="font-size: 0.9em; color: #2E7D32; margin-top: 5px; font-weight: bold;">
                        🧃 Optimizado específicamente para Reset Juice con datos históricos reales
                    </div>
                </div>
            `;
            
            stepsDiv.innerHTML = steps;
        }
    </script>
</body>
</html>
