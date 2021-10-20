# TO DO App :clipboard:

TODO App is a task management app to help you stay organized and manage your day-to-day.

## Installation

Clone the repo to install the app

```bash
git clone https://github.com/liaz98/todoApp.git
```
To run the command
```bash
python manage.py runserver
```

## Database
model.py 
![carbon](https://user-images.githubusercontent.com/33596154/138088443-ea08294c-9833-4394-8a5a-e671238c6c1a.png)

## Views
view.py

### Login view
![carbon (1)](https://user-images.githubusercontent.com/33596154/138088578-6711256b-33cd-4397-a8f7-4fdf8382cb22.png)

### Register view
![carbon (2)](https://user-images.githubusercontent.com/33596154/138088672-788e04a6-389d-49ab-800e-bc2d8f648ea9.png)

### Task List view
![carbon (3)](https://user-images.githubusercontent.com/33596154/138088703-90284ba7-aa72-4a2b-9d2e-7ad54145139f.png)

### Task Create view
```python
class TaskCreate(LoginRequiredMixin, CreateView):
    model = Task
    fields = ['title', 'description', 'complete']
    success_url = reverse_lazy('tasks')

    def form_valid(self, form):
        form.instance.user = self.request.user
        return super(TaskCreate, self).form_valid(form)
```
### Task Update view
```python
class TaskUpdate(LoginRequiredMixin, UpdateView):
    model = Task
    fields = ['title', 'description', 'complete']
    success_url = reverse_lazy('tasks')
```
### Task Delete view
```python
class TaskDelete(LoginRequiredMixin, DeleteView):
    model = Task
    context_object_name = 'task'
    success_url = reverse_lazy('tasks')
```
