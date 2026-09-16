CREATE TABLE blog_posts (
    id SERIAL PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    description TEXT NOT NULL,
    category VARCHAR(100) NOT NULL,
    publication_date DATE NOT NULL,
    author VARCHAR(100) NOT NULL,
    image_url TEXT NOT NULL,
    likes INTEGER DEFAULT 0,
    comments INTEGER DEFAULT 0,
    display_order INTEGER DEFAULT 0
);
INSERT INTO blog_posts (
    title,
    description,
    category,
    publication_date,
    author,
    image_url,
    likes,
    comments,
    display_order
)
VALUES (
    'Global Climate Summit Addresses Urgent Climate Action',
    'World leaders gathered at the Global Climate Summit to discuss urgent climate action, emissions reductions, and renewable energy targets.',
    'Environment',
    '2023-10-10',
    'Jane Smith',
    '/src/assets/climate.png',
    14000,
    204,
    1
);

CREATE TABLE team (
    id SERIAL PRIMARY KEY,
    image_url TEXT NOT NULL,
    name VARCHAR NOT NULL,
    category VARCHAR NOT NULL,
    date VARCHAR NOT NULL,
    title VARCHAR NOT NULL,
    description VARCHAR NOT NULL,
    display_order INTEGER DEFAULT 0
);
CREATE TABLE video (
    id SERIAL PRIMARY KEY,
    image_url TEXT NOT NULL,
    title VARCHAR NOT NULL,
    description VARCHAR NOT NULL,
    display_order INTEGER DEFAULT 0
); 
CREATE TABLE ai_healthcare_section (
    id SERIAL PRIMARY KEY,
    intro_title VARCHAR(255) DEFAULT 'Introduction',
    intro_text TEXT,
    main_title VARCHAR(255) DEFAULT 'Artificial Intelligence (AI)',
    main_text_1 TEXT,
    main_text_2 TEXT,
    analytics_title VARCHAR(255) DEFAULT 'Predictive Analytics and Disease Prevention',
    analytics_text TEXT
);

-- Исправленный INSERT: теперь каждое значение попадает строго в свою колонку
INSERT INTO ai_healthcare_section (
    intro_text, 
    main_text_1, 
    main_text_2, 
    analytics_text
) VALUES (
    'Artificial Intelligence (AI) has emerged as a transformative force in the healthcare industry, reshaping patient care, diagnostics, and research. In this blog post, we explore the profound impact of AI in healthcare, from revolutionizing diagnostic accuracy to enhancing patient outcomes.',
    'Artificial Intelligence (AI) has permeated virtually every aspect of our lives, and healthcare is no exception. The integration of AI in healthcare is ushering in a new era of medical practice, where machines complement the capabilities of healthcare professionals, ultimately improving patient outcomes and the efficiency of the healthcare system. In this blog post, we will delve into the diverse applications of AI in healthcare, from diagnostic imaging to personalized treatment plans, and address the ethical considerations surrounding this revolutionary technology.',
    'Artificial Intelligence (AI) has permeated virtually every aspect of our lives, and healthcare is no exception. The integration of AI in healthcare is ushering in a new era of medical practice, where machines complement the capabilities of healthcare professionals, ultimately improving patient outcomes and the efficiency of the healthcare system. In this blog post, we will delve into the diverse applications of AI in healthcare, from diagnostic imaging to personalized treatment plans, and address the ethical considerations surrounding this revolutionary technology.',
    'One of the most prominent applications of AI in healthcare is in diagnostic imaging. AI algorithms have demonstrated remarkable proficiency in interpreting medical images such as X-rays, MRIs, and CT scans. They can identify anomalies and deviations that might be overlooked by the human eye. This is particularly valuable in early disease detection. For instance, AI can aid radiologists in detecting minute irregularities in mammograms or identifying critical findings in chest X-rays.'
);
CREATE TABLE IF NOT EXISTS blog_meta_info (
    id SERIAL PRIMARY KEY,
    publication_date VARCHAR(100) DEFAULT 'October 15, 2023',
    category VARCHAR(100) DEFAULT 'Healthcare',
    reading_time VARCHAR(50) DEFAULT '10 Min',
    author_name VARCHAR(150) DEFAULT 'Dr. Emily Walker'
);

-- Наполнение данными строго по изображению
INSERT INTO blog_meta_info (publication_date, category, reading_time, author_name)
VALUES ('October 15, 2023', 'Healthcare', '10 Min', 'Dr. Emily Walker');
