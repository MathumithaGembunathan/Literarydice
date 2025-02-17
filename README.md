# Literarydice
~~~
pip install gradio
import random
import gradio as gr
def get_books_within_rating(genre, min_rating, max_rating):
    books_within_rating = []
    for i, j in data.iterrows():
        genres = j['genre'].split(', ')
        for gen in genres:
            if gen == genre and (min_rating <= j['rating'] <= max_rating):
                books_within_rating.append((j['book_title'], j['rating']))
    return books_within_rating

def random_books_in_genre_and_rating(genre, min_rating, max_rating):
    books_within_rating = get_books_within_rating(genre, min_rating, max_rating)
    if len(books_within_rating) >= 5:
        random_books = random.sample(books_within_rating, 5)
    else:
        random_books = books_within_rating
    return random_books

def genre_recommendation_chatbot(genre, min_rating, max_rating):
    random_books_list = random_books_in_genre_and_rating(genre, min_rating, max_rating)
    books_info = []
    for i, (book, rating) in enumerate(random_books_list, start=1):
        books_info.append(f"{i}. {book} (Rating: {rating})")
    return "\n".join(books_info)
~~~
# Sample
![image](https://github.com/user-attachments/assets/1ca476b1-7cb8-4973-bac8-4011360a8be0)
