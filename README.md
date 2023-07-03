- 👋 Hi, I’m @Jaji-Bandaru
- from flask import Flask, render_template, request

app = Flask(__name__)

# Routes
@app.route('/')
def home():
    return render_template('index.html')

@app.route('/courses')
def courses():
    # Add logic to fetch and display courses
    return render_template('courses.html')

@app.route('/courses/<int:course_id>')
def course_details(course_id):
    # Add logic to fetch and display course details
    return render_template('course_details.html', course_id=course_id)

@app.route('/contact', methods=['GET', 'POST'])
def contact():
    if request.method == 'POST':
        # Handle form submission and send email or save data to a database
        name = request.form['name']
        email = request.form['email']
        message = request.form['message']
        # Add logic to handle the form submission
        
        return render_template('contact.html', success=True)
    
    return render_template('contact.html', success=False)


