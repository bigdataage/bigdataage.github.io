
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Yong Peng's CV</title>
    <style>
        /* 全局重置与基础样式 - 使用相对单位提升适配性 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            transition: all 0.2s ease-in-out;
        }

        /* 定义基础字体大小，方便响应式调整 */
        :root {
            --base-font-size: 16px;
            --container-padding: 50px;
            --text-color: #2d3748;
            --primary-color: #0a0b6f;
            --light-bg: #f8f9fa;
        }

        body {
            font-family: 'Segoe UI', 'Microsoft YaHei', Arial, sans-serif;
            line-height: 1.7;
            color: var(--text-color);
            background: linear-gradient(180deg, #f8f9fa 0%, #e9ecef 100%);
            padding: 1rem; /* 使用rem相对单位 */
            max-width: 1200px;
            margin: 0 auto;
            min-height: 100vh;
            font-size: var(--base-font-size);
            /* 确保body层级不影响段落对齐 */
            text-align: left;
        }

        /* 容器样式 - 响应式内边距和圆角 */
        .cv-container {
            background: white;
            padding: var(--container-padding);
            border-radius: clamp(8px, 1.5vw, 12px); /* 自适应圆角 */
            box-shadow: 0 4px clamp(10px, 2vw, 20px) rgba(0, 0, 0, 0.08);
            position: relative;
            overflow: hidden;
            margin: 0 auto;
        }

        /* 顶部装饰条 */
        .cv-container::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: clamp(4px, 0.5vw, 6px);
            background: linear-gradient(90deg, var(--primary-color) 0%, #2a2b9f 100%);
        }

        /* 标题样式 - 响应式字体大小 */
        h1 {
            color: var(--primary-color);
            margin-bottom: clamp(30px, 3vw, 40px);
            border-bottom: clamp(2px, 0.2vw, 3px) solid var(--primary-color);
            padding-bottom: clamp(10px, 1vw, 15px);
            font-size: clamp(1.8em, 3vw, 2.2em); /* 自适应字体大小 */
            font-weight: 700;
            letter-spacing: 0.5px;
            text-align: center;
        }

        h3 {
            color: var(--primary-color);
            margin: clamp(30px, 3vw, 40px) 0 clamp(15px, 1.5vw, 20px);
            position: relative;
            padding-left: clamp(10px, 1vw, 15px);
            border-left: clamp(4px, 0.3vw, 5px) solid var(--primary-color);
            font-size: clamp(1.2em, 1.8vw, 1.4em);
            font-weight: 600;
            text-align: left;
        }

        /* 头像样式 - 完全响应式，防止变形 */
        .profile-img {
            float: right;
            height: auto; /* 取消固定高度 */
            max-height: clamp(180px, 25vw, 300px); /* 最大高度自适应 */
            width: auto;
            max-width: 100%;
            margin-left: clamp(20px, 2vw, 30px);
            margin-bottom: clamp(15px, 1.5vw, 20px);
            border-radius: clamp(4px, 0.5vw, 8px);
            box-shadow: 0 clamp(2px, 0.3vw, 4px) clamp(8px, 1vw, 12px) rgba(0, 0, 0, 0.15);
            border: clamp(2px, 0.2vw, 3px) solid #f0f2f8;
        }

        /* 段落样式 - 强制两端对齐（核心修改） */
        p {
            margin-bottom: clamp(10px, 1vw, 12px);
            text-indent: 2em;
            font-size: clamp(1em, 1.2vw, 1.05em);
            color: #4a5568;
            /* 强制两端对齐 - 核心样式 */
            text-align: justify !important;
            text-justify: inter-ideograph !important;
            word-break: break-word;
            hyphens: auto;
            /* 确保英文也能两端对齐 */
            word-spacing: 0.05em;
        }

        /* 出版物特殊样式 */
        .publication-highlight {
            background-color: #f7f8fc;
            padding: clamp(6px, 0.8vw, 8px);
            border-radius: clamp(4px, 0.5vw, 6px);
            margin: clamp(6px, 0.8vw, 8px) 0;
            /* 继承两端对齐 */
            text-align: justify !important;
            text-justify: inter-ideograph !important;
        }

        /* 链接样式 - 移动端取消hover背景 */
        a {
            color: var(--primary-color);
            text-decoration: none;
            border-bottom: 1px dotted var(--primary-color);
            transition: all 0.3s ease;
        }

        a:hover {
            color: #2a2b9f;
            border-bottom: 1px solid #2a2b9f;
            /* 仅在非移动端显示hover背景 */
            @media (min-width: 768px) {
                background-color: #f0f2f8;
                padding: 2px 4px;
                border-radius: 2px;
            }
        }

        /* 表格样式 - 深度响应式优化 */
        .skills-table-wrapper {
            width: 100%;
            overflow-x: auto; /* 横向滚动适配小屏幕 */
            -webkit-overflow-scrolling: touch; /* 移动端顺滑滚动 */
            margin: clamp(20px, 2vw, 25px) 0;
            border-radius: clamp(6px, 0.8vw, 8px);
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
        }

        table {
            width: 100%;
            border-collapse: collapse;
            min-width: 600px; /* 保证表格最小宽度，小屏幕可滚动 */
        }

        th {
            background: linear-gradient(180deg, var(--primary-color) 0%, #1a1b8f 100%);
            color: white;
            font-weight: 600;
            padding: clamp(12px, 1.2vw, 15px);
            text-align: center;
            border: none;
            font-size: clamp(0.95em, 1.1vw, 1.05em);
        }

        td {
            border: 1px solid #e2e8f0;
            padding: clamp(10px, 1.2vw, 14px) clamp(8px, 1vw, 15px);
            text-align: center;
            font-size: clamp(0.9em, 1.1vw, 1.02em);
        }

        tr:nth-child(even) {
            background-color: #fafbff;
        }

        tr:hover {
            background-color: #eef2ff;
            /* 移动端取消hover缩放，避免布局抖动 */
            @media (min-width: 768px) {
                transform: scale(1.005);
            }
        }

        /* 技能等级说明样式 */
        .skill-level-desc {
            text-indent: 0;
            margin-bottom: clamp(20px, 2vw, 25px);
            font-weight: 500;
            color: var(--text-color);
            background-color: #f0f2f8;
            padding: clamp(8px, 1vw, 10px) clamp(12px, 1.2vw, 15px);
            border-radius: clamp(4px, 0.5vw, 6px);
            /* 强制两端对齐 */
            text-align: justify !important;
            text-justify: inter-ideograph !important;
        }

        /* 清除浮动 */
        .clearfix::after {
            content: "";
            display: table;
            clear: both;
        }

        /* 强调文本样式 */
        b {
            color: var(--primary-color);
        }

        /* 响应式断点设计 - 覆盖全设备尺寸 */
        /* 大屏显示器 (1200px+) */
        @media (min-width: 1200px) {
            body {
                padding: 2rem;
            }
        }

        /* 平板横屏 (992px - 1199px) */
        @media (max-width: 1199px) {
            :root {
                --container-padding: 35px;
            }
            .profile-img {
                max-height: 250px;
            }
        }

        /* 平板竖屏 (768px - 991px) */
        @media (max-width: 991px) {
            :root {
                --container-padding: 25px;
            }
            .profile-img {
                max-height: 220px;
            }
            /* 平板端仍保持两端对齐，仅调整换行逻辑 */
            p {
                word-break: break-all;
            }
        }

        /* 普通手机 (480px - 767px) */
        @media (max-width: 767px) {
            :root {
                --container-padding: 20px;
                --base-font-size: 15px;
            }
            .profile-img {
                float: none;
                display: block;
                margin: 0 auto clamp(20px, 2vw, 25px);
                max-height: 200px;
            }
            h1 {
                font-size: clamp(1.7em, 4vw, 1.9em);
                margin-bottom: clamp(20px, 2.5vw, 25px);
            }
            h3 {
                font-size: clamp(1.1em, 2vw, 1.3em);
                margin: clamp(25px, 2.5vw, 30px) 0 clamp(12px, 1.2vw, 15px);
            }
        }

        /* 小屏手机 (≤479px) */
        @media (max-width: 479px) {
            :root {
                --container-padding: 15px;
                --base-font-size: 14px;
            }
            body {
                padding: 0.5rem;
            }
            .profile-img {
                max-height: 180px;
            }
            h1 {
                font-size: clamp(1.5em, 4.5vw, 1.7em);
            }
            h3 {
                font-size: clamp(1em, 2vw, 1.2em);
                padding-left: 8px;
                border-left-width: 3px;
            }
            td, th {
                padding: 8px 6px;
            }
        }
    </style>
</head>
<body>
    <div class="cv-container clearfix">
        <h1><b>Yong Peng's CV</b></h1> 

        <img src="http://github.com/bigdataage/bigdataage.github.io/raw/master/yongpengyi.png" 
             class="profile-img" 
             alt="Yong Peng's photo"/>   

        <h3><b>1. About Me</b></h3>   
        <p>Full Name: Yong Peng (彭勇)</p>
        <p>Place of Birth: <a href="https://en.wikipedia.org/wiki/Yibin"> Yibin </a> of <a href="https://en.wikipedia.org/wiki/Sichuan">Sichuan</a> Province, <a href="https://en.wikipedia.org/wiki/China"> P. R. China. </a></p>
        <p>Citizenship: China</p>
        <p>Email: yongp@outlook.com</p>
        <p>GitHub: <a href="https://github.com/CTLife"> https://github.com/CTLife </a></p> 
        <p>ORCID:  <a href="https://orcid.org/0000-0003-3405-8836">  https://orcid.org/0000-0003-3405-8836 </a></p>


        <hr>
        <h3><b>2. Research Interests</b></h3>
        <p>The <b> epigenetic regulatory network </b> (ERN), characterized by the intricate and dynamic crosstalk among epigenomes and epitranscriptomes, plays a crucial role in precisely regulating spatiotemporal gene expression, which is fundamental for cellular division, differentiation, and senescence. The ERN also serves as a fundamental and multifunctional interface that integrates environmental signals with intrinsic genetic programs. Therefore, the ERN disorders are considered as a primary cause of aging and can be reversed or slowed through therapeutic interventions. My research mainly focuses on ERN dysregulation in aging and aging-related diseases, alongside epigenetic mechanisms governing the biosynthesis and bioactivity of active components derived from <b> Chinese Materia Medica </b> (CMM) and medicinal natural products.</p>
        <p>(1)	<b> ERN in Aging and Aging-related Diseases </b></p>                
        <p>Utilizing a combination of experimental and computational multi-omics methods to dissect the mechanisms of epitranscriptome-epigenome crosstalk as edges of ERN, such as interplay among RNA modifications (e.g., m6A,Ψ,m5C), DNA modifications (e.g., 5mC, 5hmC, 6mA), and histone modifications (e.g., H3K27me3,H3K27ac,H3K9me3), as well as functional roles of ERN in aging and aging-related diseases.</p> 
        <p>(2) <b> ERN in Bioactivity of CMM </b></p>               
        <p>Explore how Chinese herbal medicines and medicinal natural products delay aging, extend lifespan and healthspan by restoring ERN homeostasis and correcting (recoding) ERN disorders in aging and aging-related diseases. To provide novel insights into the multi-component and multi-target pharmacological mechanisms of <b> traditional Chinese medicine </b> (TCM) and establish epigenetic reprogramming as a promising therapeutic strategy for delaying aging or treating aging-related diseases.</p>   
        <p>(3) <b> ERN in Biosynthesis of CMM </b></p>             
        <p>Explore how ERN modulates biosynthesis of high-value active components derived from CMM and medicinal natural products. Develop large-scale plant multi-omics data analysis and AI approaches to facilitate rapid identification of unknown metabolic pathways and enzymes involved in the production of novel bioactive compounds for delaying aging and treating aging-related diseases.</p>  
        <p>(4)	<b> ERN in Liquid Biopsy </b></p>                    
        <p>Develop novel liquid biopsy strategies by integrating cell-free epitranscriptome and epigenome for early diagnosis and detection of aging-related diseases, thereby providing a molecular foundation for the concept of evidence-based medicine and the characteristics of precision medicine in TCM.</p>  


        <hr>
        <h3><b>3. Experience</b></h3> 
        <p>2025.07~now,  &nbsp; Associate Professor,  Innovative Institute of Chinese Medicine and Pharmacy, Institute of Herbgenomics @ <a href="https://www.cdutcm.edu.cn/">  Chengdu University of Traditional Chinese Medicine </a> , Chengdu, China.</p>
        <p>2025.02~2025.04,  &nbsp; Assistant Researcher,  Cancer Research Center @ <a href="https://www.fudan.edu.cn/en/"> Fudan University </a>, Shanghai, China.</p>
        <p>2019.12~2025.01,  &nbsp; Postdoctoral Researcher, <a href="http://he-group.uchicago.edu/"> Chuan He Group </a> @ Department of Chemistry, and <a href="http://www.mengjiechen.com/"> Mengjie Chen Group </a> @ Department of Medicine, <a href="https://www.uchicago.edu/">The University of Chicago</a>, Chicago, IL 60637, USA.</p>
        <p>2019.02~2019.11,  &nbsp; <a href="http://www.cls.edu.cn/info/1263/1105.htm"> Jie Qiao Group </a> @ Peking University Third Hospital, Beijing, China.</p>                     


        <hr>
        <h3><b>4. Education</b></h3>
        <p>Ph. D., &nbsp; 2013.09~2019.01,  &nbsp; Integrative Life Sciences,  &nbsp; <a href="http://www.cls.edu.cn/en/">Peking-Tsinghua Center for Life Sciences</a> and <a href="http://www.aais.pku.edu.cn">AAIS</a> @ <a href="https://en.wikipedia.org/wiki/Peking_University">Peking University</a>, Beijing, China. (2013.07-2013.12 Rotation; 2014.01-2017.04 Aibin He Lab; 2017.05-2019.01 Jie Qiao Lab)</p> 
        <p>M. Sc., &nbsp; 2010.09~2013.06,  &nbsp; Physics,  &nbsp; <a href="http://wlxy.imu.edu.cn/"> School of Physical Science and Technology</a> @ <a href="https://en.wikipedia.org/wiki/Inner_Mongolia_University">Inner Mongolia University</a>, Hohhot, China.</p>
        <p>B. Sc., &nbsp; 2006.09~2010.06,  &nbsp; Biotechnology,  &nbsp; School of Life Sciences @ <a href="https://en.wikipedia.org/wiki/Heilongjiang_University">Heilongjiang University</a>, Haerbin, China.</p>  
        <p>PhD. Dissertation (Chinese): Epigenetic Outcomes of Assisted Reproduction in the Offspring. @ <a href="http://www.cls.edu.cn/info/1263/1105.htm"> Jie Qiao Group </a>.</p>
        <p>M. Sc. thesis (Chinese):Predicting subnuclear location of proteins and subcellular location of ncRNAs based on multi-information fusion and multi-label ensemble classifier. @ <a href="https://wlxy.imu.edu.cn/info/1029/4019.htm"> Qianzhong Li Group </a>.</p>  
        <p>B. Sc. thesis (Chinese): Optimize the nitrogen sources of a red pigment-producing strain for generating more pigments. @ <a href="https://xueshu.baidu.com/scholarID/CN-BR7321PJ"> Tao Jin Group </a>.</p>


        <hr>
        <h3><b>5. Peer Reviewed Publications and Submitted Manuscripts</b></h3>    
        <p><b>(#) First authorship; (*) Senior authorship</b></p>
        <p><b style = "color:#0a0b6f"> Selected publications: </b></p> 
        <p class="publication-highlight">[8] Andrew Shafik#*, <b>Yong Peng#</b>, Zijie Zhang, Chen Chang, Pingluan Wang, Junghwa Lim, Hongjun Song, Chuan He, Mengjie Chen* & Peng Jin*. 2026.  <a href="https://www.nature.com/articles/s41593-025-02112-z"> Multi-region m6A epitranscriptome profiling of the human brain reveals both spatial and temporal signatures and an association with disease-risk genes. </a>  Nature Neuroscience, 29(1):195-205.   <a href="https://pubmed.ncbi.nlm.nih.gov/41366183/">PMID: 41366183</a></p>
        <p class="publication-highlight">[7] Xiao Jiang#, Chu Xu#, Enzhuo Yang#, Danhua Xu#, <b>Yong Peng#</b>, Zhuo Liu, Qinxin Shao, Xue Han, Qiuxiao Chen, Weizhi He, Shuang He, Yanhui Xu, Chuan He, Xinxin Huang* & Lulu Hu*. 2025.  <a href="https://doi.org/10.1093/procel/pwaf079"> Deciphering the RNA Landscapes on Mammalian Cell Surfaces. </a>  Protein & Cell.   <a href="https://pubmed.ncbi.nlm.nih.gov/40973153/">PMID: 40973153</a></p>
        <p class="publication-highlight">[6] <b>Yong Peng#</b>, Jason Karpus#, Jyoti D. Patel, Everett E. Vokes, Marina Chiara Garassino, Zhou Zhang, Wei Zhang, Mengjie Chen, Chuan He*, Christine M. Bestvina*. 2025.  <a href="https://onlinelibrary.wiley.com/doi/10.1002/cac2.12606"> Epigenomic exploration of disease status of EGFR-mutated non-small cell lung cancer using plasma cell-free DNA hydroxymethylomes. </a>  Cancer Communications, 45(1):51-55.   <a href="https://pubmed.ncbi.nlm.nih.gov/39527101/">PMID: 39527101</a></p>
        <p class="publication-highlight">[5] <b>Yong Peng#</b>, Hanzhe Meng#, Ruiqi Ge#, Shun Liu#, Mengjie Chen, Chuan He* & Lulu Hu*. 2022. 
        <a href="https://www.sciencedirect.com/science/article/pii/S2666166722005573"> Detection of m6A RNA modifications at single-nucleotide resolution using m6A-selective allyl chemical labeling and sequencing. </a>  STAR Protocols, 3(4), 101677. <a href="https://pubmed.ncbi.nlm.nih.gov/36112507/">PMID: 36112507</a></p>
        <p class="publication-highlight">[4] Lulu Hu#, Shun Liu#, <b>Yong Peng#</b>, Ruiqi Ge#, Rui Su#, Chamara Senevirathne, Bryan T. Harada, Qing Dai, Jiangbo Wei, Lisheng Zhang, Ziyang Hao, Liangzhi Luo, Huanyu Wang, Yuru Wang, Minkui Luo, Mengjie Chen*, Jianjun Chen* & Chuan He*. 2022. <a href="https://www.nature.com/articles/s41587-022-01243-z"> m6A RNA modifications are measured at single-base resolution across the mammalian transcriptome. </a>  Nature Biotechnology. <a href="https://pubmed.ncbi.nlm.nih.gov/35288668/">PMID: 35288668</a></p>
        <p class="publication-highlight">[3] Siming Kong#, <b>Yong Peng#</b>, Wei Chen#, Xinyi Ma,Yuan Wei, Yangyu Zhao, Rong Li, Jie Qiao*, Liying Yan*. 2020. <a href="https://onlinelibrary.wiley.com/doi/full/10.1002/ctm2.234"> Epigenetic Consequences of Hormonal Interactions between Opposite-sex Twin Fetuses. </a>  Clinical and Translational Medicine, 10(8): e234. <a href="https://pubmed.ncbi.nlm.nih.gov/33377650/">PMID: 33377650</a></p>
        <p class="publication-highlight">[2] Wei Chen#, <b>Yong Peng#</b>, Xinyi Ma#, Siming Kong, Shuangyan Tan,Yuan Wei,Yangyu Zhao, Wenxin Zhang, Yang
        Wang*, Liying Yan*, Jie Qiao*. 2020. <a href="https://www.thelancet.com/journals/ebiom/article/PIIS2352-3964(20)30452-7/fulltext"> Integrated Multi-omics Reveal Epigenomic Disturbance of Assisted Reproductive Technologies in Human Offspring. </a>  eBioMedicine, 61, 103076. <a href="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7585147/">PMID:33099088</a></p>
        <p class="publication-highlight">[1] Shanshan Ai#, <b>Yong Peng#</b>, Chen Li, Fei Gu, Xianhong Yu, Yanzhu Yue, Qing Ma, Jinghai Chen, Zhiqiang Lin, Pingzhu Zhou, Huafeng Xie, Terence W Prendiville, Wen Zheng,Yuli Liu, Stuart H Orkin, Da-Zhi Wang, Jia Yu,William T Pu*, Aibin He*. 2017. 
        <a href="https://elifesciences.org/content/6/e24570">
        EED orchestration of heart maturation through interaction with HDACs is H3K27me3-independent. </a>   
        eLife, 6:e24570. <a href="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5400508/">PMID:28394251</a></p>

                                  
        <hr>
        <p><b style = "color:#0a0b6f"> Other publications: </b></p> 
        <p>[13]. Alex Wardale, <b>Yong Peng</b>, Ruiqi Ge, Tor Erik Jørgensen, Steinar Daae Johansen, Chuan He & Igor Babiak. 2026.  Single-nucleotide resolution mapping of m6A of zebrafish mRNAs in early embryonic development links m6A modifications to the maternal-to-zygotic transition.  (Available on bioRXiv, doi: <a href="https://doi.org/10.1101/2025.11.19.688951"> https://doi.org/10.1101/2025.11.19.688951 </a> )</p> 
        <p>[12]. Daniel A. Kuppers, Sonali Arora, Cindy L. Wladyka, Ruiqi Ge, Shun Liu, <b>Yong Peng</b>, Rui Su, Anne Wilhite, Jianjun Chen, Chuan He, Andrew C. Hsieh & Patrick J. Paddison. 2026.  N6-methyladenosine regulation of mRNA translation is essential for early human erythropoiesis.  (Available on bioRXiv, doi: <a href="https://doi.org/10.1101/2025.11.10.687731"> https://doi.org/10.1101/2025.11.10.687731 </a> )</p> 
        <p>[11]. Jong Jin Jeong#, Trinath Das#, Shannon Delaney, John Froehlich, Xiu Chen, Linda Degenstein, Ahri Choe, Prasanth Kumar Punathil Kannan, Hyun Lee, Kith Pradhan, Srinivas Aluri, <b>Yong Peng</b>, Alana Beadell, Charith Wickrema, Jagadeesh Ramasamy, Sriram Sundarave, Chuan He, Amit Verma & Amittha Wickrema. 2026.  Inhibition of TET2 phosphorylation activates fetal hemoglobin in sickle cell 1 disease.  Nature Communications, under review.</p>
        <p>[10]. Weizhi He#, Chu Xu#, Wen Chen#, Yuhang Wang, <b>Yong Peng</b>, Shujuan Chang, Wei Zhu，Jiuhong Kang* & Lulu Hu*. 2025. <a href="https://link.springer.com/article/10.1186/s13059-025-03857-3"> Uli-epic: profiling RNA modifications from ultra-low input samples. </a> Genome biology, 26, 384. <a href="https://pubmed.ncbi.nlm.nih.gov/41219823/"> PMID:41219823 </a></p>
        <p>[9]. Yutao Zhao, Sun Hui-Lung, Wenlong Li, Chang Ye, Xiaoyang Dou, <b>Yong Peng</b>, Tong Wu, Pingluan Wang, Cheng-Wei Ju, Shun Liu, Yu-Hao Zhong, Qing Dai, Kinga Pajdzik & Chuan He. 2025. <a href="https://www.nature.com/articles/s41467-025-64668-5"> Pseudouridylation of 7SK by PUS7 regulates Pol II transcription elongation. </a> Nature Communications, 16, 9595. <a href="https://pubmed.ncbi.nlm.nih.gov/41168165/"> PMID:41168165 </a></p>
        <p>[8]. Ruiqi Ge#, Chang Ye#, <b>Yong Peng</b>, Qing Dai, Yutao Zhao, Shun Liu, Pingluan Wang, Lulu Hu* & Chuan He*. 2022. <a href="https://www.nature.com/articles/s41596-022-00765-9"> m6A-SAC-seq for quantitative whole transcriptome m6A profiling. </a>   Nature Protocols, 18(2), 626-657. <a href="https://pubmed.ncbi.nlm.nih.gov/37349502/"> PMID:37349502 </a></p>
        <p>[7]. Hanshuang Li#,Chunshen Long#,Yan Hong, Lemuge Chao,<b>Yong Peng</b>, and Yongchun Zuo*. 2022. <a href="https://www.mdpi.com/1422-0067/23/3/1567"> The Cumulative Formation of R-loop Interacts with Histone Modifications to Shape Cell Reprogramming. </a>    International Journal of Molecular Sciences, 23(3):1567.  <a href="https://pubmed.ncbi.nlm.nih.gov/35163490/">PMID:35163490</a></p>
        <p>[6]. Zhiqiang Yan#, Jianting An#, <b>Yong Peng</b>, Siming Kong, Qiang Liu, Ming Yang, Qilong He, Shi Song, Yidong Chen, Wei Chen, Rong Li, Jie Qiao*, Liying Yan*. 2021. <a href="https://academic.oup.com/bib/advance-article-abstract/doi/10.1093/bib/bbab208/6294163?redirectedFrom=fulltext"> DevOmics: an integrated multi-omics database of human and mouse early embryo. </a> Briefings in Bioinformatics, bbab208.  <a href="https://pubmed.ncbi.nlm.nih.gov/34097004/">PMID:34097004</a></p>
        <p>[5]. Chengchuan Ma, Rong Niu, Tianxiao Huang, Li-Wa Shao, <b>Yong Peng</b>, Wanqiu Ding, Ye Wang, Guifang Jia, Chuan He, Chuan-Yun Li, Aibin He, and Ying Liu*. 2018. <a href="https://www.nature.com/articles/s41556-018-0238-5">N6-methyldeoxyadenine is a transgenerational epigenetic signal for mitochondrial stress adaptation. </a> Nature Cell Biology, 21(3):319-327.  <a href="https://www.ncbi.nlm.nih.gov/pubmed/30510156">PMID:30510156</a></p>
        <p>[4] Shanshan Ai#, Xianhong Yu#, Yumei Li#, <b>Yong Peng</b>, Chen Li, Yanzhu Yue, Ge Tao, Chuan-Yun Li, William T Pu*, and Aibin He*. 2017. 
        <a href="http://circres.ahajournals.org/content/early/2017/05/16/CIRCRESAHA.117.311212">
        Divergent Requirements for EZH1 in Heart Development Versus Regeneration. </a>   
        Circulation Research, 121(2):106-112. <a href="https://www.ncbi.nlm.nih.gov/pubmed/28512107">PMID:28512107</a></p>
        <p>[3]  Yong-Chun Zuo*, <b>Yong Peng</b>, Li Liu, Wei Chen, Lei Yang*, and Guo-Liang Fan*. 2014.  
        <a href="http://www.sciencedirect.com/science/article/pii/S0003269714001912">
        Predicting peroxidase subcellular location by hybridizing different descriptors of Chou’ pseudo amino acid patterns. </a>
        Analytical Biochemistry, 458:14-19.  <a href="https://www.ncbi.nlm.nih.gov/pubmed/24802134">PMID:24802134</a></p>
        <p>[2]  Yongchun Zuo*, Pengfei Zhang, Li Liu, Tao Li, <b>Yong Peng</b>, Guangpeng Li, and Qianzhong Li*. 2014.  
        <a href="http://link.springer.com/article/10.1007%2Fs10577-014-9414-z">
        Sequence-specific flexibility organization of splicing flanking sequence and prediction of splice sites in the human genome. </a>
        Chromosome Research, 22(3):321-334.  <a href="https://www.ncbi.nlm.nih.gov/pubmed/24728765">PMID:24728765</a></p>
        <p>[1] Tao Li, Qian-Zhong Li*, Shuai Liu, Guo-Liang Fan, Yong-Chun Zuo, and <b>Yong Peng</b>. 2013.  
        <a href="http://bioinformatics.oxfordjournals.org/content/29/6/678.abstract">
        PreDNA: accurate prediction of DNA-binding sites in proteins by integrating sequence and geometric structure information. </a>
        Bioinformatics, 29(6):678-685.  <a href="https://www.ncbi.nlm.nih.gov/pubmed/23335013">PMID:23335013</a></p>


        <hr>
        <h3><b>6. Blog</b></h3>                                                                         
        <p>English Blog: <a href="http://yongpeng.org"> http://yongpeng.org </a></p>               
        <p>Chinese Blog: <a href="http://blog.sciencenet.cn/u/bigdataage"> http://blog.sciencenet.cn/u/bigdataage </a></p>       

        <h3><b>7. Skills</b></h3>  
        <p class="skill-level-desc"><b>7 Levels from Newbie 1 to God Level 7:</b><br> 1:Newbie, &nbsp;  2:Basic, &nbsp;  3:Familiar, &nbsp;   4:Professional, &nbsp;  5:Very Professional, &nbsp; 6:Top 10 Experts, &nbsp;  7:God Level (Surpassing human's limit).</p>         

        <div class="skills-table-wrapper">
            <table> 
                <tr>              
                    <th> Skill </th>
                    <th> Level </th> 
                    <th>  </th>
                    <th> Skill </th>
                    <th> Level </th>   
                    <th>  </th>
                    <th> Skill </th>
                    <th> Level </th> 
                </tr>     
                <tr>
                    <td> Python </td>
                    <td> 3 </td>
                    <th>  </th>
                    <td> Mojo </td>
                    <td> 1 </td>
                    <th>  </th>
                    <td> Snakemake/Containers </td>
                    <td> 2 </td>
                </tr>  
                <tr>
                    <td> R </td>
                    <td> 4 </td>
                    <th>  </th>
                    <td> Julia </td>
                    <td> 1 </td>
                    <th>  </th>
                    <td> SQL and noSQL </td>
                    <td> 1 </td>
                </tr>
                <tr>
                    <td> Perl </td>
                    <td> 4 </td>
                    <th>  </th>
                    <td> Linux Bash Shell </td>
                    <td> 3 </td>
                    <th>  </th>
                    <td> Markup Languages </td>
                    <td> 1 </td>
                </tr>
                <tr>
                    <td> C </td>
                    <td> 2 </td>
                    <th>  </th>
                    <td> C++ </td>
                    <td> 1 </td>
                    <th>  </th>
                    <td> Go </td>
                    <td> 2 </td>
                </tr>
                <tr>
                    <td>  </td>
                    <td>  </td>
                    <th>  </th>
                    <td>  </td>
                    <td>  </td>
                    <th>  </th>
                    <td>  </td>
                    <td>  </td>
                </tr>
                <tr>
                    <td> Statistics </td>
                    <td> 3 </td>
                    <th>  </th>
                    <td> Statistical Physics </td>
                    <td> 2 </td>
                    <th>  </th>
                    <td> Molecular Simulation </td>
                    <td> 1 </td>
                </tr>
                <tr>
                    <td> Complex Networks </td>
                    <td> 2 </td>
                    <th>  </th>
                    <td> Nonlinear Dynamics </td>
                    <td> 1 </td>
                    <th>  </th>
                    <td> Systems Biology </td>
                    <td> 2 </td>
                </tr>
                <tr>
                    <td> Machine Learning </td>
                    <td> 2 </td>
                    <th>  </th>
                    <td> Deep Neural Networks </td>
                    <td> 1 </td>
                    <th>  </th>
                    <td> Artificial Intelligence </td>
                    <td> 1 </td>
                </tr>
                <tr>
                    <td> Bioinformatics </td>
                    <td> 4 </td>
                    <th>  </th>
                    <td> Epigenetics </td>
                    <td> 3 </td>
                    <th>  </th>
                    <td> Quantitative Genetics </td>
                    <td> 2 </td>
                </tr>
                <tr>
                    <td> Biology </td>
                    <td> 3 </td>
                    <th>  </th>
                    <td> English </td>
                    <td> 3 </td>
                    <th>  </th>
                    <td> TCM </td>
                    <td> 2 </td>
                </tr>
            </table>


        <div class="footer">
            <hr>
            <hr>
            End! 没啦！
            <hr>
            <hr>
        </div>
</div>

